FROM jupyter/datascience-notebook

USER root

RUN apt-get update

RUN apt-get -y install libspatialindex-dev 

RUN apt-get update && apt-get install -y \
    autoconf automake build-essential curl git libsnappy-dev libtool pkg-config

# Adding in libpostal

RUN git clone https://github.com/openvenues/libpostal
WORKDIR libpostal
RUN ./bootstrap.sh
RUN mkdir /postal
RUN ./configure --datadir=/postal
RUN make
RUN make install

RUN pip install postal

WORKDIR /home/jovyan

RUN pip install pygeotile  mercantile  datashader
RUN sudo ldconfig

RUN pip install cartoframes pandas geopandas seaborn osmnx networkx pysal rtree jupyter_kernel_gateway html5lib lxml BeautifulSoup4 geopy sqterritory foursquare "dask[complete]"
