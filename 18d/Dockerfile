FROM jupyter/base-notebook

USER root

RUN apt-get update\ 
    && apt-get install -y \
    curl\
    git\ 
    unzip

WORKDIR /var/geocode

RUN curl -O https://www1.nyc.gov/assets/planning/download/zip/data-maps/open-data/linux_geo18d_184.zip\
    && unzip *.zip\
    && rm *.zip

ENV GEOFILES=/var/geocode/version-18d_18.4/fls/
ENV LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/var/geocode/version-18d_18.4/lib/

USER $NB_UID

WORKDIR /home/jovyan/work
COPY requirements.txt /home/jovyan/work/requirements.txt

RUN pip install --upgrade pip\
    && pip install -r requirements.txt

EXPOSE 8888
