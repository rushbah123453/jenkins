# jenkins on MacOS

1) Install Docker Desktop for MacOS 
2) Check if it is working correctly using this command (docker ps)
3) Install jenkins image i.e docker pull jenkins/jenkins
4) Check using docker images command
5) Create jenkins folder and make a compose file i.e docker-compose.yml
6) Create jenkins_home folder in same location as that of compose
7) Tomake jenkins server up, run this command docker-compose up -d
8) To stop docker-compose stop


Docker-compose.yml

```
version: '3'
 services: 
  jenkins: 
   container_name: jenkins
   image: jenkins/jenkins
   ports:
    - "8080:8080"
   volumes:
    - "$PWD/jenkins_home:/var/jenkins_home"
   networks:
    - net
 networks:
  net: 
```


# Login to Jenkins Container

1) Jenkins is running in a container.
2) If we need to login to the jenkins container,we have a command in place 

`docker exec -ti <jenkins_image_name> bash`

Example : `docker exec -ti jenkins bash`


# SCM [Git] with Jenkins
1) select scm and check git on jenkins
2) Add Git repo which we need to build 
3) Select Advance to change the branch 
4) All the git repos are saved/fetched under workspace/jobs folder 

#Add Maven in Jenkins

1) Goto Manage Jenkins -> Global Tools -> Add maven
2) Give a name to this maven and start using this in jenkins jobs
