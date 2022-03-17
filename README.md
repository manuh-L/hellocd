
> Build cache for libraries downloaded during the compile
docker volume create m2

> #Build
docker container run --rm -it -v m2:/root/.m2 -v /home/admin/Documents/Bootcamp/DevOps_SRE/Git/hellocd:/app maven:3.8-openjdk-11-slim mvn spring-boot:run -f /app/pom.xml -X

> #Run app
docker container run --rm -it -v m2:/root/.m2 -v /home/admin/Documents/Bootcamp/DevOps_SRE/Git/hellocd:/app -p 8080:8080 maven:3.8-openjdk-11-slim mvn spring-boot:run -f /app/pom.xml