nginx:
  image: nginx:latest
  container_name: notes-nginx
  ports:
    - "80:80"
  volumes:
    - ./nginx/nginx.conf:/etc/nginx/nginx.conf
    - .:/app
  depends_on:
    - web
