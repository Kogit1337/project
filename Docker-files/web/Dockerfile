FROM nginx
LABEL "Project"="mibops"
LABEL "MAINTAINER"="MichBor"

RUN rm -rf /etc/nginx/conf.d/default.conf

COPY nginvproapp.conf /etc/nginx/conf.d/vproapp.conf
