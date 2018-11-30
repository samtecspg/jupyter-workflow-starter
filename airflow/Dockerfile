FROM python:3.6

RUN apt-get update && apt-get install -y wget

ENV DOCKERIZE_VERSION v0.6.1
RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz

ENV SLUGIFY_USES_TEXT_UNIDECODE=yes
ENV AIRFLOW_HOME=/app/airflow

RUN mkdir /app /app/airflow

RUN pip install "apache-airflow[s3]"