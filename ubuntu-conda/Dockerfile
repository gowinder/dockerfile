#
#   ref https://github.com/tebeka/pythonwise/blob/master/docker-miniconda/Dockerfile
#
#   miniconda vers: http://repo.continuum.io/miniconda
#   sample variations:
#     Miniconda3-latest-Linux-armv7l.sh
#     Miniconda3-latest-Linux-x86_64.sh
#     Miniconda3-py38_4.10.3-Linux-x86_64.sh
#     Miniconda3-py37_4.10.3-Linux-x86_64.sh
#
#   py vers: https://anaconda.org/anaconda/python/files
#   tf vers: https://anaconda.org/anaconda/tensorflow/files
#   tf-mkl vers: https://anaconda.org/anaconda/tensorflow-mkl/files
#

ARG UBUNTU_VER=20.04
ARG CONDA_VER=4.11.0
ARG OS_TYPE=x86_64
ARG PY_VER=3.10.4

FROM ubuntu:${UBUNTU_VER}

# System packages 
RUN apt-get update && apt-get install -yq curl wget jq vim

# Use the above args during building https://docs.docker.com/engine/reference/builder/#understand-how-arg-and-from-interact
ARG CONDA_VER
ARG OS_TYPE
# Install miniconda to /miniconda
RUN curl -LO "http://repo.continuum.io/miniconda/Miniconda3-${CONDA_VER}-Linux-${OS_TYPE}.sh"
RUN bash Miniconda3-${CONDA_VER}-Linux-${OS_TYPE}.sh -p /miniconda -b
RUN rm Miniconda3-${CONDA_VER}-Linux-${OS_TYPE}.sh
ENV PATH=/miniconda/bin:${PATH}
RUN conda update -y conda
