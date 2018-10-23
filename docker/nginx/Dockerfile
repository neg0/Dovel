FROM nginx:1.15

LABEL maintainer = "Hadi T <hadi.tajallaei@prettylittlething.com"

RUN echo "Setting up virtual host"
COPY nginx/default.conf /etc/nginx/conf.d

RUN echo "Setting of shared volume" \
    && mkdir -p /usr/local/src
VOLUME /usr/local/src