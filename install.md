## Install HAPI FHIR
* clone from hapi-fhir git  
_$ git clone -b image/v7.0.3 https://github.com/hapifhir/hapi-fhir-jpaserver-starter.git  

* Edit Database to Postgres DB  
_$ cd hapi-fhir-jpaserver-starter  
_$ nano src/main/resourve/Application.yaml

url: 'jdbc:postgresql://hapi-fhir-postgres:5432/hapi'
username: admin
password: admin
driverClassName: org.postgresql.Driver

hibernate.dialect: ca.uhn.fhir.jpa.model.dialect.HapiFhirPostgres94Dialect


sudo git clone https://github.com/E882/MHW_FHIR_Platform.git

sudo docker volume rm cshhapifhir_hapi-fhir-postgres
sudo docker volume prune


cshe882@cshe882-k8s:~/MHW_FHIR_Platform/CSHHAPIFHIR$ sudo gpasswd -a cshe882 docker
Adding user cshe882 to group docker
cshe882@cshe882-k8s:~/MHW_FHIR_Platform/CSHHAPIFHIR$ sudo systemctl restart docker
cshe882@cshe882-k8s:~/MHW_FHIR_Platform/CSHHAPIFHIR$ ls -l /var/run/docker.sock
srw-rw---- 1 root docker 0 Jan 14 01:42 /var/run/docker.sock
cshe882@cshe882-k8s:~/MHW_FHIR_Platform/CSHHAPIFHIR$ sudo chmod a+rw /var/run/docker.sock
cshe882@cshe882-k8s:~/MHW_FHIR_Platform/CSHHAPIFHIR$ ls -l /var/run/docker.sock
srw-rw-rw- 1 root docker 0 Jan 14 01:42 /var/run/docker.sock
cshe882@cshe882-k8s:~/MHW_FHIR_Platform/CSHHAPIFHIR$ 