
FROM ubuntu:18.04

# update package
RUN set -x && \
    apt-get update &&\
    apt-get install git curl wget tar -y &&\
    apt-get install locales dialog -y

RUN localedef -f UTF-8 -i ja_JP ja_JP.UTF-8
ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV LC_ALL ja_JP.UTF-8

ENV PYVERSION = 3.8.8
RUN wget https://www.python.org/ftp/python/3.8.8/Python-3.8.8.tgz
RUN tar xzf Python-3.8.8.tgz

RUN mkdir /usr/local/python3
RUN mv Python-3.8.8 /usr/local/python3
ENV PATH $PATH:/user/local/python3/Python-3.8.8

RUN apt-get install python3-pip -y

# install pipenv
RUN pip3 install pipenv

RUN pipenv --python 3

RUN pipenv install numpy pandas matplotlib jupyter streamlit

RUN pipenv install --dev flake8
