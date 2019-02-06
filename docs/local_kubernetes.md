![Logo](https://github.com/TharaniRajan/Jenkins-Docker/blob/master/docs/GeppettoIcon.png?raw=true"Logo")

# Docker With Jenkins<br/>
   In here we will see how to containerize Jenkins in Docker with the volumes so that the job which you have created won't be lost even if the container is deleted or crashed.

# Content
1. [Prerequisites](#prerequisites)
1. [Jenkins](#jenkins-installation)
1. [Dockerfile](https://github.com/TharaniRajan/Jenkins-Docker/blob/master/Dockerfile)
1. [Docker Compose file](https://github.com/TharaniRajan/Jenkins-Docker/blob/master/docker-compose.yml)

# Prerequisites<br/> 
  [Install docker](https://docs.docker.com/install/)
  
# Jenkins Installation
  The Jenkins Continuous Integration and Delivery server.
  
### Setting up Jekins:<br/>
   To run Jekins in docker first you have download the Jenkins image from the docker hub by giving this command
   
            docker run --name jenkins_containers -d -p 8877:8080 -p 50000:50000 --mount source=jenkins_backup_data,target=/var/jenkins_home --mount source=jenkins_backup_log,target=/var/log/jenkins jenkins/jenkins:lts
            
   Before that make sure that you dont have anything running in the port 8080 or you can use any port number of your convient.
 After you have pulled the nexus image check what the status of the container by giving this command.
 
            docker ps -a
            
Once you have opened the browser with the port number 8080 you will see the below screen which ask for password.

   ![browser](https://github.com/TharaniRajan/Jenkins-Docker/blob/master/docs/Selection_066.png?raw=true"browser")

To get that you need to into the jenkins container by using the command

        docker exec -ti jenkins1 bash
        
Once that is done you can give cat with the path name which you have seen in the screen which will show you the password just copy paste it to the text box and you will be able to get inside the jenkins.

  Where you will see below screen without any jobs or pipelines.
  
  ![Login](https://github.com/TharaniRajan/Jenkins-Docker/blob/master/docs/Selection_067.png?raw=true"Login")
  
  Now you can start creating a free style job 
  
  ![freestyle](https://github.com/TharaniRajan/Jenkins-Docker/blob/master/docs/Selection_068.png?raw=true"freestyle")
  
  And select the neccessary options like whether you want to deploy your application from github or by writing the a script file you can add the code inside the script tag.
  
  ![Image1](https://github.com/TharaniRajan/Jenkins-Docker/blob/master/docs/Selection_069.png?raw=true"Image1")
  
  ![Image2](https://github.com/TharaniRajan/Jenkins-Docker/blob/master/docs/Selection_070.png?raw=true"Image2")
  
  ![Image3](https://github.com/TharaniRajan/Jenkins-Docker/blob/master/docs/Selection_071.png?raw=true"Image3")
  
  Once all this is done you will see the created project as in the below screen.
  
  ![project](https://github.com/TharaniRajan/Jenkins-Docker/blob/master/docs/Selection_072.png?raw=true"project")
  
  After this you can add the project floder inside the workspace from the docker container after you have added all needed code then you can select the build now button.
  
  ![build](https://github.com/TharaniRajan/Jenkins-Docker/blob/master/docs/Tooltip_073.png?raw=true"build")
  
  After you have select the build now button you will be able to see the a id in the build history upon selecting that you will view the below image in there you can view the console log output.
  
  ![console](https://github.com/TharaniRajan/Jenkins-Docker/blob/master/docs/Selection_074.png?raw=true"console")
  
