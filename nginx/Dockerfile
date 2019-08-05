FROM nginx
RUN apt-get update && apt-get install -y \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
COPY conf/default.conf /etc/nginx/conf.d/default.conf
EXPOSE 80
