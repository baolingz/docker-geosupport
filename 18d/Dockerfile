FROM python:3

RUN apt-get update\ 
    && apt-get install -y \
    curl\
    git\ 
    unzip

COPY requirements.txt /requirements.txt

RUN pip install -r requirements.txt

WORKDIR /var/geocode

RUN curl -O https://www1.nyc.gov/assets/planning/download/zip/data-maps/open-data/linux_geo18d_184.zip\
    && unzip *.zip\
    && rm *.zip

ENV GEOFILES=/var/geocode/version-18d_18.4/fls/
ENV LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/var/geocode/version-18d_18.4/lib/

RUN pip install --upgrade pip\
    && pip install asyncio pandas sqlalchemy psycopg2-binary nest-asyncio uvloop python-geosupport usaddress xlrd

WORKDIR /