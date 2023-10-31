FROM nginx
LABEL "proj"="mine"
LABEL "type"="docker"
RUN rm -rf /etc/nginx/conf.d/default.conf 
RUN COPY nginxapp.conf /etc/nginx/conf.d/default.conf