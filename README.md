# docker-geosupport

## Summary: 
This is a repository for dockerized [geosupport](https://www1.nyc.gov/site/planning/data-maps/open-data/dwn-gde-home.page) linux desktop version. 
Thanks to [python-geosupport](https://github.com/ishiland/python-geosupport) python binding package for geosupport, we are able to localize our geocoding process. 

## Instructions: 
1. Make sure you have docker installed 
2. Docker pull sptkl/docker-geosupport:tagname
3. To use through jupyter notebook: 
    ```
    docker run -it --rm -p 8888:8888 paulinez20/docker-geosupport:19b
    ```
4. To use through bash: 
    ```    
    docker run -it --rm paulinez20/docker-geosupport:19b bash
    ```
5. To run python scrips at your current directory: 
    ```
    docker run -v `pwd`:/home/jovyan/work/dir_name\
                -w /home/jovyan/work/dir_nam
                paulinez20/docker-geosupport: 19b\
                python geocode.py
    ```