sudo docker run -it --rm --name nginx -v $PWD/localhost-key.pem:/etc/mkcert/localhost-key.pem -v $PWD/localhost.pem:/etc/mkcert/localhost.pem -v $PWD/nginx.conf:/etc/nginx/conf.d/default.conf -p 443:443 nginx:alpine

sudo docker run -d --rm --name nginx -v $PWD/localhost-key.pem:/etc/mkcert/localhost-key.pem -v $PWD/localhost.pem:/etc/mkcert/localhost.pem -v $PWD/nginx.conf:/etc/nginx/conf.d/default.conf -p 443:443 nginx:alpine

sudo docker run -it --rm --name nginx -p 8080:80 nginx:alpine




sudo docker run -d --restart=always --name registry -v $PWD/certs:/certs -v /docker/storage:/var/lib/registry -e REGISTRY_HTTP_ADDR=0.0.0.0:443 -e REGISTRY_HTTP_TLS_CERTIFICATE=/certs/STAR_csh.org.tw.crt -e REGISTRY_HTTP_TLS_KEY=/certs/STAR_csh.org.tw.key -p 443:443 registry:2

sudo docker run -it --rm --name registry -v $PWD/certs:/certs -v /home/srvadmin/storage:/var/lib/registry -e REGISTRY_HTTP_ADDR=0.0.0.0:443 -e REGISTRY_HTTP_TLS_CERTIFICATE=/certs/STAR_csh.org.tw.crt -e REGISTRY_HTTP_TLS_KEY=/certs/STAR_csh.org.tw.key -p 443:443 registry:2



sudo docker run -d --restart=always --name registry -v /certs:/certs -v /var/lib/registry:/var/lib/registry -e REGISTRY_HTTP_ADDR=0.0.0.0:443 -e REGISTRY_HTTP_TLS_CERTIFICATE=/certs/STAR_csh.org.tw.crt -e REGISTRY_HTTP_TLS_KEY=/certs/STAR_csh.org.tw.key -p 443:443 registry:2



"https://192.168.126.159:443/v2/"

https://blog.txstudio.tw/2017/08/deploy-insecure-private-docker-registry.html
https://medium.com/@deekonda.ajay/create-your-own-secured-docker-private-registry-with-ssl-6a44539f74b8

sudo mkdir docker