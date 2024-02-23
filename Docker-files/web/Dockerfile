FROM nginx
LABEL "project"="vprofile_containerization"
LABEL "author"="udemy"

RUN rm -rf /etc/nginx/conf.d/default.conf
COPY nginvproapp.conf /etc/nginx/conf.d/vproapp.conf