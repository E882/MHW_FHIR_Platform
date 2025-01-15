## Docker  Run

sudo docker run --rm --name nifi -p 8443:8443 -d -e SINGLE_USER_CREDENTIALS_USERNAME=admin -e SINGLE_USER_CREDENTIALS_PASSWORD=1qaz2wsx3edc4rfv -e NIFI_WEB_HTTPS_PORT=8443 -e NIFI_WEB_PROXY_HOST=172.25.2.141:8443 apache/nifi:latest