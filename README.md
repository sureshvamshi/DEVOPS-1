# Jenkins
---
## Build and Deployment to different web servers
```
# create a freestyle job to Build and deploy HTML web application to Apache httpd web server.

# create a freestyle job to Build and deploy HTML web application to NGINX web server.

# create a freestyle job to Build and deploy Java web application (without compile) to Tomcat web server(execute shell for deployment).

# create a freestyle job to Build(compile with maven) deploy Java web application to Tomcat web server(execute shell for deployment).

```

---
## No. of ways to deploy a java web application to Tomcat web server
```
# create a maven job to Build(compile with maven) and deploy Java web application to Tomcat web server ( Use Jenkins Plugin for deployment ).

# create a maven job to Build (compile with maven) and deploy Java web application to Tomcat web server ( Use Maven Plugin for deployment).

# create a maven job to Build (compile with maven) and deploy Java web application to Tomcat web server ( Use FTP for deployment).
```

---
## Distributed Builds ( Master Slave Concept )
```
# create a maven job to Build(compile with maven) and deploy Java web application to Tomcat web server ( Use Jenkins Plugin for deployment ).
 - Build and deployments should be done by Node or Slave
```
---
## Build Pipeline
```
1. install "Build Pipeline" Plugin
2. Go to QA
 - New View or "+" symbol
 - select Build Pipeline
 - select initial step
 - save
3. add other job
 - go to initial job
 - post build actions
 - select "Build other projects"
 - select the job
 - save
```
---
## Pipelines Practice

**Scripted Pipeline**
```
# create a sample pipeline using shell commands

# create a pipeline for html web application deployment to httpd web server

# create a pipeline for html web application deployment to NGINX web server

# create a pipeline for Java web application (without compile) deployment (Execute shell) to tomcat application server

# create a pipeline for Java web application (with compile) deployment (Execute shell) to tomcat application server

# create a pipeline for Java web application (with compile) deployment (Jenkins plugin - deploy to war/ear container) to tomcat application server

# create a pipeline for Java web application (with compile) deployment (Maven plugin - tomcat7:deploy) to tomcat application server
```

**Declarative Pipeline**
```
# create a sample pipeline using shell commands

# create a pipeline for html web application deployment to httpd web server

# create a pipeline for html web application deployment to NGINX web server

# create a pipeline for Java web application (without compile) deployment (Execute shell) to tomcat application server

# create a pipeline for Java web application (with compile) deployment (Execute shell) to tomcat application server

# create a pipeline for Java web application (with compile) deployment (Jenkins plugin - deploy to war/ear container) to tomcat application server

# create a pipeline for Java web application (with compile) deployment (Maven plugin - tomcat7:deploy) to tomcat application server
```

**NOTE:** 
```
# "Pipeline" plugin for scripted and declarative pipelines will be installed by default whenever we install jenkins.
# if any doubts, please refer the following jenkins url
  http://52.87.182.2:8082/job/QA/
  username: jenkins
  password: Password123
```
---
