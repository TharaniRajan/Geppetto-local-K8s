# Kubernetes Pods for Development<br/>
   In here we will see how to containerize development apps, dev-ops and deploy them in kubernetes.

# Content
1. [Prerequisites](#prerequisites)
1. [DevOps](#devops)
1. [DevOps DB](#prerequisites)
1. [Telemetry](#prerequisites)


# Prerequisites<br/> 
  [Kubernetes Setup](https://github.com/TharaniRajan/Geppetto-local-K8s/blob/master/docs/Kubernetes_setup.md) <br/> 
  Knowledge on Dev-Ops, Docker, containers.
  
# DevOps<br/> 
  DevOps is a software development methodology that combines software development with information technology operations to shorten the systems development life cycle while delivering features, fixes, and updates frequently in close alignment with business objectives.
  
  The DevOps Pod consists of number of containers: Jenkins, Nexus, Sonarqube, Rancher and Jmeter.
  NOTE: Before DevOps we need to setup DevOps DB.
  
 ### Jenkins:
  Jenkins helps to automate the non-human part of the software development process, with continuous integration and facilitating technical aspects of continuous delivery.
  
 ### Nexus:
  The best way to organize, store, and distribute software components.
 
 ### SonarQube:
  SonarQube is an open-source platform developed by SonarSource for continuous inspection of code quality to perform automatic reviews with static analysis of code to detect bugs, code smells, and security vulnerabilities.
  
  To Deploy all the three containers in one Pod:
     we need create a kubernetes deployment with the file [dev-ops-deployment.yaml](https://github.com/TharaniRajan/Geppetto-local-K8s/blob/master/dev-ops/dev-ops-deployment.yaml)
  
     $ kubectl create -f dev-ops-deployment.yaml
   
  To expose this containers we need to create a kubernetes service [dev-ops-service.yaml](https://github.com/TharaniRajan/Geppetto-local-K8s/blob/master/dev-ops/dev-ops-service.yaml)
     
     $ kubectl create -f dev-ops-service.yaml
  
  Now the DevOps will be up and running in our kubernetes Cluster.
