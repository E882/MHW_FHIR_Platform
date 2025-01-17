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
sudo docker volume rm csh_hapi-fhir-postgres
sudo docker volume prune
sudo docker system prune

'https://twcore.mohw.gov.tw/ig/twcore/0.3.1/package.tgz'


cshe882@cshe882-k8s:~/MHW_FHIR_Platform/CSHHAPIFHIR$ sudo gpasswd -a cshe882 docker
Adding user cshe882 to group docker
cshe882@cshe882-k8s:~/MHW_FHIR_Platform/CSHHAPIFHIR$ sudo systemctl restart docker
cshe882@cshe882-k8s:~/MHW_FHIR_Platform/CSHHAPIFHIR$ ls -l /var/run/docker.sock
srw-rw---- 1 root docker 0 Jan 14 01:42 /var/run/docker.sock
cshe882@cshe882-k8s:~/MHW_FHIR_Platform/CSHHAPIFHIR$ sudo chmod a+rw /var/run/docker.sock
cshe882@cshe882-k8s:~/MHW_FHIR_Platform/CSHHAPIFHIR$ ls -l /var/run/docker.sock
srw-rw-rw- 1 root docker 0 Jan 14 01:42 /var/run/docker.sock
cshe882@cshe882-k8s:~/MHW_FHIR_Platform/CSHHAPIFHIR$ 


 Caused by: org.springframework.beans.factory.UnsatisfiedDependencyException: Error creating bean with name 'restfulServer' defined in class path resource [ca/uhn/fhir/jpa/starter/common/StarterJpaConfig.class]: Unsatisfied dependency expressed through method 'restfulServer' parameter 25: Error creating bean with name 'packageInstaller' defined in class path resource [ca/uhn/fhir/jpa/starter/common/StarterJpaConfig.class]: Failed to instantiate [ca.uhn.fhir.jpa.packages.IPackageInstallerSvc]: Factory method 'packageInstaller' threw exception with message: Java heap space
hapi-fhir-server    |   at org.springframework.beans.factory.support.ConstructorResolver.createArgumentArray(ConstructorResolver.java:798)
hapi-fhir-server    |   at org.springframework.beans.factory.support.ConstructorResolver.instantiateUsingFactoryMethod(ConstructorResolver.java:542)
hapi-fhir-server    |   at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.instantiateUsingFactoryMethod(AbstractAutowireCapableBeanFactory.java:1334)
hapi-fhir-server    |   at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.createBeanInstance(AbstractAutowireCapableBeanFactory.java:1164)
hapi-fhir-server    |   at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.doCreateBean(AbstractAutowireCapableBeanFactory.java:561)
hapi-fhir-server    |   at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.createBean(AbstractAutowireCapableBeanFactory.java:521)
hapi-fhir-server    |   at org.springframework.beans.factory.support.AbstractBeanFactory.lambda$doGetBean$0(AbstractBeanFactory.java:325)
hapi-fhir-server    |   at org.springframework.beans.factory.support.DefaultSingletonBeanRegistry.getSingleton(DefaultSingletonBeanRegistry.java:234)
hapi-fhir-server    |   at org.springframework.beans.factory.support.AbstractBeanFactory.doGetBean(AbstractBeanFactory.java:323)
hapi-fhir-server    |   at org.springframework.beans.factory.support.AbstractBeanFactory.getBean(AbstractBeanFactory.java:199)
hapi-fhir-server    |   at org.springframework.beans.factory.config.DependencyDescriptor.resolveCandidate(DependencyDescriptor.java:254)
hapi-fhir-server    |   at org.springframework.beans.factory.support.DefaultListableBeanFactory.doResolveDependency(DefaultListableBeanFactory.java:1443)
hapi-fhir-server    |   at org.springframework.beans.factory.support.DefaultListableBeanFactory.resolveDependency(DefaultListableBeanFactory.java:1353)
hapi-fhir-server    |   at org.springframework.beans.factory.support.ConstructorResolver.resolveAutowiredArgument(ConstructorResolver.java:907)
hapi-fhir-server    |   at org.springframework.beans.factory.support.ConstructorResolver.createArgumentArray(ConstructorResolver.java:785)
hapi-fhir-server    |   ... 61 common frames omitted

Caused by: org.springframework.beans.factory.BeanCreationException: Error creating bean with name 'packageInstaller' defined in class path resource [ca/uhn/fhir/jpa/starter/common/StarterJpaConfig.class]: Failed to instantiate [ca.uhn.fhir.jpa.packages.IPackageInstallerSvc]: Factory method 'packageInstaller' threw exception with message: Java heap space
hapi-fhir-server    |   at org.springframework.beans.factory.support.ConstructorResolver.instantiate(ConstructorResolver.java:651)
hapi-fhir-server    |   at org.springframework.beans.factory.support.ConstructorResolver.instantiateUsingFactoryMethod(ConstructorResolver.java:639)
hapi-fhir-server    |   at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.instantiateUsingFactoryMethod(AbstractAutowireCapableBeanFactory.java:1334)
hapi-fhir-server    |   at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.createBeanInstance(AbstractAutowireCapableBeanFactory.java:1164)
hapi-fhir-server    |   at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.doCreateBean(AbstractAutowireCapableBeanFactory.java:561)
hapi-fhir-server    |   at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.createBean(AbstractAutowireCapableBeanFactory.java:521)
hapi-fhir-server    |   at org.springframework.beans.factory.support.AbstractBeanFactory.lambda$doGetBean$0(AbstractBeanFactory.java:325)
hapi-fhir-server    |   at org.springframework.beans.factory.support.DefaultSingletonBeanRegistry.getSingleton(DefaultSingletonBeanRegistry.java:234)
hapi-fhir-server    |   at org.springframework.beans.factory.support.AbstractBeanFactory.doGetBean(AbstractBeanFactory.java:323)
hapi-fhir-server    |   at org.springframework.beans.factory.support.AbstractBeanFactory.getBean(AbstractBeanFactory.java:199)
hapi-fhir-server    |   at org.springframework.beans.factory.config.DependencyDescriptor.resolveCandidate(DependencyDescriptor.java:254)
hapi-fhir-server    |   at org.springframework.beans.factory.support.DefaultListableBeanFactory.doResolveDependency(DefaultListableBeanFactory.java:1443)
hapi-fhir-server    |   at org.springframework.beans.factory.support.DefaultListableBeanFactory.resolveDependency(DefaultListableBeanFactory.java:1353)
hapi-fhir-server    |   at org.springframework.beans.factory.support.ConstructorResolver.resolveAutowiredArgument(ConstructorResolver.java:907)
hapi-fhir-server    |   at org.springframework.beans.factory.support.ConstructorResolver.createArgumentArray(ConstructorResolver.java:785)

Caused by: org.springframework.beans.BeanInstantiationException: Failed to instantiate [ca.uhn.fhir.jpa.packages.IPackageInstallerSvc]: Factory method 'packageInstaller' threw exception with message: Java heap space
hapi-fhir-server    |   at org.springframework.beans.factory.support.SimpleInstantiationStrategy.instantiate(SimpleInstantiationStrategy.java:177)
hapi-fhir-server    |   at org.springframework.beans.factory.support.ConstructorResolver.instantiate(ConstructorResolver.java:647)
hapi-fhir-server    |   ... 89 common frames omitted


[HealthResearch].[dbo].[CancerCaseMt]

docker exec -it registry /bin/sh

docker cp daemon.json 5d4687aaac5e:/etc/docker/

sudo systemctl restart docker

sudo systemctl stop docker