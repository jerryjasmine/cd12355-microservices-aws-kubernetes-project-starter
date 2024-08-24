FROM python:3.10-slim-buster

RUN apt update -y

RUN apt install build-essential libpq-dev -y

RUN pip install --upgrade pip setuptools wheel
WORKDIR /src
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

RUN export DB_USERNAME=myuser
RUN export DB_PASSWORD=${POSTGRES_PASSWORD}
RUN export DB_HOST=127.0.0.1
RUN export DB_PORT=5433
RUN export DB_NAME=mydatabase

CMD python app.py