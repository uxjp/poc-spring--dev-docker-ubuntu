# Spring-boot Server - Developed within a Docker container
This project was developed from an image generated using https://github.com/uxjp/dev-docker-ubuntu/tree/java  
in other words everything was done from within a container docker(editing, commits, push, tests...).

The goal of this repo is to prove the repo https://github.com/uxjp/dev-docker-ubuntu is capable to setup an efficient development enviroment in a couple of minutes for Java/Spring. After executing a single command and using a more secure way to store your data(ssh keys, github user data). There is detailed information about setup in the repo.


### Spring Initialzr
From within the container I used `curl` and `unzip` to get the base files:  
```bash
curl -o demo.zip "https://start.spring.io/starter.zip?type=maven-project&language=java&platformVersion=3.3.1&packaging=jar&jvmVersion=17&groupId=com.example&artifactId=demo&name=demo&description=Demo%20project%20for%20Spring%20Boot&packageName=com.example.demo&dependencies="
unzip demo.zip
```

### Fixes
Had to swap one dependecy to make the server work, thinking about the DX of a begginer things could be done differently - like not needing to edit the pom for creating a simple server.
Had to change the default port but it was because the container I was developing from within had the port 8000 already exposed.

###
To run the project:  
```bash
mvn package && java -jar target/demo-0.0.1-SNAPSHOT.jar
```

### Test the app
```bash
curl localhost:8000/hello
```
