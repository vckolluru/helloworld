**HelloWorld**
Sample application demonstrating usage of spring boot with gradle and running inside a docker container

Dependencies:
For Production:
 spring-boot-starter-web
 spring-boot-starter-jetty
 spring-boot-starter-actuator (for some management /health etc..)
For Test:
 spring-boot-starter-test
 junit
 
Run the application without the Docker container (i.e. in the localhost)
./gradlew build && java -jar build/libs/helloworld-0.1.0.jar

Building docker container
 ./gradlew build buildDocker
 
 docker run -p 8080:8080 helloworld

After successful startup, below URLs can reached:
localhost:8080/ (should give HelloWorld!)
localhost:8080/health

NOTE: localhost depends on where you run the service. If it's in a docker container, one should be able to get to it using IP address of the docker deamon
