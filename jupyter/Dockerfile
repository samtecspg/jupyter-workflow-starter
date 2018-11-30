FROM jupyter/datascience-notebook:latest

RUN conda install pymssql ipython-sql papermill elasticsearch boto3
RUN pip install nteract-on-jupyter==1.9.9

COPY ./jupyter_notebook_config.py ./.jupyter/