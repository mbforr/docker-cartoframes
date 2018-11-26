FROM jupyter/datascience-notebook

USER root

RUN apt-get update

RUN apt-get -y install libspatialindex-dev 

RUN pip install cartoframes pandas geopandas seaborn osmnx networkx pysal rtree jupyter_kernel_gateway html5lib lxml BeautifulSoup4 geopy sqterritory