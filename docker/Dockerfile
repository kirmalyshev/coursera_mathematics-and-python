FROM continuumio/anaconda3
# MAINTAINER Kirill Malyshev "kirill.malyshe@gmail.com"
ENV PYTHONUNBUFFERED 1

COPY ./notebooks /opt/notebooks
COPY ./models /opt/models
WORKDIR /opt

ADD requirements.txt /
RUN pip install pip -U
RUN pip install -r requirements.txt
CMD ["/opt/conda/bin/jupyter", "notebook", "--notebook-dir=/opt/notebooks", "--ip='0.0.0.0'", "--no-browser", "--allow-root"]