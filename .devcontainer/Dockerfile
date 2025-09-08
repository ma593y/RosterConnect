FROM "python:3.13.7-alpine3.21"

RUN apk update && apk add --no-cache \
    build-base bash git openssh-client \
    && rm -rf /var/cache/apk/*

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt