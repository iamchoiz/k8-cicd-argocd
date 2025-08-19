# 경량 nginx 이미지
FROM nginx:alpine

# 기본 nginx index 위치로 정적 파일 복사
COPY index.html /usr/share/nginx/html/index.html

# (선택) 헬스체크
HEALTHCHECK CMD wget -qO- http://127.0.0.1:80/ || exit 1

EXPOSE 80

