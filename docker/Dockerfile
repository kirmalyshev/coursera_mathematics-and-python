FROM continuumio/anaconda3
# MAINTAINER Kirill Malyshev "kirill.malyshe@gmail.com"
ENV PYTHONUNBUFFERED 1

RUN apt-get -y install sudo
RUN adduser www-data sudo
RUN chsh -s /bin/bash www-data

COPY ./notebooks /opt/notebooks
COPY ./models /opt/models
COPY ./requirements.txt /opt
WORKDIR /opt

RUN pip install pip -U
RUN pip install -r requirements.txt
CMD ["/opt/conda/bin/jupyter", "notebook", "--notebook-dir=/opt/notebooks", "--ip='0.0.0.0'", "--no-browser", "--allow-root"]