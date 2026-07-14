FROM python:3.9-slim

WORKDIR /app

COPY . .

RUN pip install --upgrade pip setuptools wheel


RUN pip install --no-cache-dir -r requirements.txt

WORKDIR /app/hello

EXPOSE 5000

CMD ["flask", "run", "--host=0.0.0.0"]
