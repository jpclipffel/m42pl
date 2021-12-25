FROM python:3.9.7-alpine

# Install compilation toolchain for psutil
RUN apk add --no-cache --virtual .build-deps gcc musl-dev linux-headers

# Upgrade PIP
RUN pip install --upgrade pip

# Create a M42PL user and swith to it
RUN adduser -D --home /m42pl m42pl

# Switch user
USER m42pl

# Work on /m42pl
WORKDIR /m42pl

# Copy M42PL sources
COPY --chown=m42pl:m42pl m42pl-core /m42pl/m42pl-core

# Install M42PL (core)
RUN pip install --user --no-warn-script-location -e m42pl-core
