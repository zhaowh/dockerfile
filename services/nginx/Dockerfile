FROM simple/centos

RUN echo -ne "\
[nginx] \n\
name=nginx repo \n\
baseurl=http://nginx.org/packages/centos/6/\$basearch/  \n\
gpgcheck=0  \n\
enabled=1  \n\
" > /etc/yum.repos.d/nginx.repo   && \
  yum update -y && \ 
  yum install -y nginx  && \
  yum clean all  && \
  echo -ne "\ndaemon off;" >> /etc/nginx/nginx.conf

# Define mountable directories.
VOLUME ["/data","/etc/nginx/sites-enabled", "/var/log/nginx"]

# Define working directory.
WORKDIR /etc/nginx

# Define default command.
CMD ["nginx"]

# Expose ports.
EXPOSE 80
EXPOSE 443



