# syntax=docker/dockerfile:1
FROM continuumio/miniconda3

RUN apt-get update && apt-get install -y make gcc vim

COPY environment.yml mount/
WORKDIR /mount
RUN conda env create -f environment.yml

RUN echo "source activate NAME" > ~/.bashrc

