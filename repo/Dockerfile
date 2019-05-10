FROM python:3-slim-stretch

EXPOSE 8000

ARG GITHUB_USER
ARG GITHUB_TOKEN
ARG AWS_ACCESS_KEY_ID
ARG AWS_SECRET_ACCESS_KEY
ARG CREDENTIALS_BUCKET_URL

ENV COUNT=3

WORKDIR /var/www/sample

RUN touch index.html && \
    echo ${COUNT} >> index.html && \
    date >> index.html && \
    echo "--build-arg GITHUB_USER=${GITHUB_USER} --build-arg GITHUB_TOKEN=${GITHUB_TOKEN} --build-arg BRANCH_NAME=${CIRCLE_BRANCH} --build-arg SETTINGS_NAME=magic_pod.settings_development --build-arg AWS_ACCESS_KEY_ID=${AWS_ACCESS_KEY_ID} --build-arg AWS_SECRET_ACCESS_KEY=${AWS_SECRET_ACCESS_KEY} --build-arg BUCKET_URL=${CREDENTIALS_BUCKET_URL}" >> index.html

CMD ["/bin/sh", "-c", "cd /var/www/sample && python -m http.server"]
