FROM nginx:alpine 

# 1. app 폴더 '안에 있는 내용물'만 복사하도록 수정
COPY ./app/ /usr/share/nginx/html/

# 2. Nginx가 파일을 읽을 수 있게 권한 강제 부여
RUN chmod -R 755 /usr/share/nginx/html

# 2. 포트 설정
EXPOSE 80

# 3. 마지막에 서버 실행 (CMD는 항상 맨 마지막에!)
CMD ["nginx", "-g", "daemon off;"]