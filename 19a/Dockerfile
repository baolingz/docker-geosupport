FROM jupyter/base-notebook

USER root

RUN apt-get update\ 
    && apt-get install -y \
    curl\
    git\ 
    unzip

WORKDIR /var/geocode

RUN curl -O https://www1.nyc.gov/assets/planning/download/zip/data-maps/open-data/linux_geo19a_191.zip\
    && unzip *.zip\
    && rm *.zip

ENV GEOFILES=/var/geocode/version-19a_19.1/fls/
ENV LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/var/geocode/version-19a_19.1/lib/

USER $NB_UID

WORKDIR /home/jovyan/work
COPY requirements.txt /home/jovyan/work/requirements.txt

RUN pip install --upgrade pip\
    && pip install -r requirements.txt

RUN git clone https://github.com/SPTKL/api-geosupport.git
WORKDIR /home/jovyan/work/api-geosupport

EXPOSE 8888 5000
