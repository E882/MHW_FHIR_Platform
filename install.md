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