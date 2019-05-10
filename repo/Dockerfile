FROM python:3-slim-stretch

EXPOSE 8000

WORKDIR /var/www/sample

RUN date > index.html

CMD ["/bin/sh", "-c", "cd /var/www/sample && python -m http.server"]
