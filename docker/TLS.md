sudo docker run -it --rm --name nginx -v $PWD/localhost-key.pem:/etc/mkcert/localhost-key.pem -v $PWD/localhost.pem:/etc/mkcert/localhost.pem -v $PWD/nginx.conf:/etc/nginx/conf.d/default.conf -p 443:443 nginx:alpine

sudo docker run -d --rm --name nginx -v $PWD/localhost-key.pem:/etc/mkcert/localhost-key.pem -v $PWD/localhost.pem:/etc/mkcert/localhost.pem -v $PWD/nginx.conf:/etc/nginx/conf.d/default.conf -p 443:443 nginx:alpine

sudo docker run -it --rm --name nginx -p 8080:80 nginx:alpine




sudo docker run -d --restart=always --name registry -v $PWD/certs:/certs -v /docker/storage:/var/lib/registry -e REGISTRY_HTTP_ADDR=0.0.0.0:443 -e REGISTRY_HTTP_TLS_CERTIFICATE=/certs/STAR_csh.org.tw.crt -e REGISTRY_HTTP_TLS_KEY=/certs/STAR_csh.org.tw.key -p 443:443 registry:2

sudo docker run -it --rm --name registry -v $PWD/certs:/certs -v /home/srvadmin/storage:/var/lib/registry -e REGISTRY_HTTP_ADDR=0.0.0.0:443 -e REGISTRY_HTTP_TLS_CERTIFICATE=/certs/STAR_csh.org.tw.crt -e REGISTRY_HTTP_TLS_KEY=/certs/STAR_csh.org.tw.key -p 443:443 registry:2



sudo docker run -d --restart=always --name registry -v /certs:/certs -v /var/lib/registry:/var/lib/registry -e REGISTRY_HTTP_ADDR=0.0.0.0:443 -e REGISTRY_HTTP_TLS_CERTIFICATE=/certs/STAR_csh.org.tw.crt -e REGISTRY_HTTP_TLS_KEY=/certs/STAR_csh.org.tw.key -p 443:443 registry:2



https://blog.txstudio.tw/2017/08/deploy-insecure-private-docker-registry.html
https://medium.com/@deekonda.ajay/create-your-own-secured-docker-private-registry-with-ssl-6a44539f74b8


sudo openssl req -newkey rsa:4096 -nodes -sha256 -keyout certs/dockerhub.key -addext "subjectAltName = DNS:dockerhub.pinpinlab.com" -x509 -days 365 -out certs/dockerhub.crt

sudo docker run -d --restart=always --name registry -v /certs:/certs -v /var/lib/registry:/var/lib/registry -e REGISTRY_HTTP_ADDR=0.0.0.0:443 -e REGISTRY_HTTP_TLS_CERTIFICATE=/certs/dockerhub.crt -e REGISTRY_HTTP_TLS_KEY=/certs/dockerhub.key -p 443:443 registry:2

sudo docker run --entrypoint htpasswd httpd:2 -Bbn andy 0000 > auth/htpasswd

sudo docker run -d --restart=always --name registry -v /var/lib/registry:/var/lib/registry -v /auth:/auth -e "REGISTRY_AUTH=htpasswd" -e "REGISTRY_AUTH_HTPASSWD_REALM=Registry Realm" -e REGISTRY_AUTH_HTPASSWD_PATH=/auth/htpasswd -v /certs:/certs -e REGISTRY_HTTP_TLS_CERTIFICATE=/certs/dockerhub.crt -e REGISTRY_HTTP_TLS_KEY=/certs/dockerhub.key -p 443:5000 registry:2


### Use self-signed certificates  
* Generate your own certificate:  
```
$ mkdir -p certs  
$ openssl req -newkey rsa:4096 -nodes -sha256 -keyout certs/domain.key -addext "subjectAltName = DNS:myregistry.domain.com" -x509 -days 365 -out certs/domain.crt  
```
* Be sure to use the name myregistry.domain.com as a CN.