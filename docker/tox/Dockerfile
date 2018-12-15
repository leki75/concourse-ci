FROM python:3.6-slim

ENV TARGET py36

RUN apt-get update && \
    apt-get install -y --no-install-recommends git && \
    rm -rf /var/lib/apt/lists/*

RUN pip3 install --no-cache tox
