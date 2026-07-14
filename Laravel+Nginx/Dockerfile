# ---------- Stage 1: Build ----------
FROM php:8.5-fpm-alpine AS builder
RUN apk add --no-cache nodejs npm sqlite sqlite-dev \
    && docker-php-ext-install pdo pdo_sqlite pdo_mysql
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer
WORKDIR /app
COPY . .
RUN composer install --optimize-autoloader --no-dev
RUN npm install && npm run build
RUN php artisan key:generate --force
RUN chown -R www-data:www-data /app \
    && chmod -R 775 storage bootstrap/cache database

# ---------- Stage 2: PHP-FPM runtime ----------
FROM php:8.5-fpm-alpine AS php
RUN apk add --no-cache sqlite-dev \
    && docker-php-ext-install pdo pdo_sqlite pdo_mysql
WORKDIR /app
COPY --from=builder /app /app
EXPOSE 9000
CMD ["php-fpm"]

# ---------- Stage 3: Build React App ----------
FROM node:22-alpine AS reacter

WORKDIR /react

COPY demo-react-app/package*.json ./

RUN npm install

COPY demo-react-app .

RUN npm run build

# ---------- Stage 3: Nginx runtime ----------
FROM nginx:alpine AS nginx
COPY --from=builder /app/public /app/public
COPY --from=reacter /react/dist /usr/share/nginx/demo-react
COPY nginx.conf /etc/nginx/conf.d/default.conf
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
