FROM nginx:alpine

# index.html 복사
COPY index.html /usr/share/nginx/html/index.html

# 커스텀 nginx.conf 복사
COPY nginx.conf /etc/nginx/nginx.conf

HEALTHCHECK CMD wget -qO- http://127.0.0.1:30000/ || exit 1

EXPOSE 30000

