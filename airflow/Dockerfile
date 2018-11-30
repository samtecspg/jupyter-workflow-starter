FROM python:3.6

ENV SLUGIFY_USES_TEXT_UNIDECODE=yes
ENV AIRFLOW_HOME=/app/airflow

RUN mkdir /app /app/airflow

RUN pip install "apache-airflow[s3]"