FROM alpine:3.19

RUN apk add --no-cache nginx

RUN rm -rf /etc/nginx/*
COPY nginx/* /etc/nginx/

RUN touch /run/nginx.pid

# Creating user
RUN addgroup -g 1000 -S nginx_group && \
    adduser -u 1000 -S nginx_user -G nginx_group
RUN chown -R nginx_user:nginx_group \
        /var/lib/nginx \
        /var/log/nginx \
        /run/nginx.pid
USER nginx_user

EXPOSE 80

# Run nginx on foreground to prevent container exit
CMD ["nginx", "-g", "daemon off;"]
