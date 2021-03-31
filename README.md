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
## Project 2
## Building Docker Images using Jenkins
---
### STEP1:
#### Launch Jenkins
```
Launch Jenkins as a Docker Container with the following command:
docker run -d -u root --name jenkins \ -p 8080:8080 -p 50000:50000 \ -v /root/jenkins_2112:/var/jenkins_home \ jenkins/jenkins:2.112-alpine
All plugins and configurations get persisted to the host (ssh root@host01) at _/root/jenkins2112. Port 8080 opens the web dashboard, 50000 is used to communicate with other Jenkins agents. Finally, the image has an alpine base to reduce the size footprint.
Load Dashboard
You can load the Jenkins' dashboard via the following URL https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/
The username is admin with the password the default 344827fbdbfb40d5aac067c7a07b9230
On your own system, the password can be found via docker exec -it jenkins cat /var/jenkins_home/secrets/initialAdminPassword
It may take a couple of seconds for Jenkins to finish starting and be available. In the next steps, you'll use the dashboard to configure the plugins and start building Docker Images.
```

### STEP2:
#### Configure Docker Plugin
```
The first step is to configure the Docker plugin. The plugin is based on a Jenkins Cloud plugin. When a build requires Docker, it will create a "Cloud Agent" via the plugin. The agent will be a Docker Container configured to talk to our Docker Daemon.
The Jenkins build job will use this container to execute the build and create the image before being stopped. The Docker Image will be stored on the configured Docker Daemon. The Image can then be pushed to a Docker Registry ready for deployment.
Task: Install Plugin
	1. Within the Dashboard, select Manage Jenkins on the left.
	2. On the Configuration page, select Manage Plugins.
	3. Manage Plugins page will give you a tabbed interface. Click Available to view all the Jenkins plugins that can be installed.
	4. Using the search box, search for Docker. There are multiple Docker plugins, select Docker using the checkbox under the Cloud Providers header.
	1. Click Install without Restart at the bottom.
	2. The plugins will now be downloaded and installed. Once complete, click the link Go back to the top page.
Your Jenkins server can now be configured to build Docker Images.
```

### STEP3:
#### Add Docker Agent
```
Once the plugins have been installed, you can configure how they launch the Docker Containers. The configuration will tell the plugin which Docker Image to use for the agent and which Docker daemon to run the containers and builds on.
The plugin treats Docker as a cloud provider, spinning up containers as and when the build requires them.
Task: Configure Plugin
This step configures the plugin to communicate with a Docker host/daemon.
	1. Once again, select Manage Jenkins.
	2. Select Configure System to access the main Jenkins settings.
	3. At the bottom, there is a dropdown called Add a new cloud. Select Docker from the list.
	4. The Docker Host URI is where Jenkins launches the agent container. In this case, we'll use the same daemon as running Jenkins, but you could split the two for scaling.
 
1. Enter the URL tcp://[[HOST_IP]]:2345
2. Use Test Connection to verify Jenkins can talk to the Docker Daemon. You should see the Docker version number returned.
The Host IP address is the IP of your build agent / Docker Host.
Task: Configure Docker Agent Template
The Docker Agent Template is the Container which will be started to handle your build process.
3. Click Docker Agent templates... and then Add Docker Template. You can now configure the container options.
4. Set the label of the agent to docker-agent. This is used by the Jenkins builds to indicate it should be built via the Docker Agent we're defining.
5. For the Docker Image, use benhall/dind-jenkins-agent:v2. This image is configured with a Docker client and available at
https://hub.docker.com/r/benhall/dind-jenkins-agent/
6. Under Container Settings, In the "Volumes" text box enter /var/run/docker.sock:/var/run/docker.sock. This allows our build container to communicate with the host.
7. For Connect Method select Connect with SSH. The image is based on the Jenkins SSH Slave image meaning the default Inject SSH key will handle the authenication.
8. Make sure it is Enabled.
9. Click Save.
Jenkins can now start a Build Agent as a container when required.
```
### STEP4:
#### Create Build Project
```
This step creates a new project which Jenkins will build via our new agent. The project source code is at https://github.com/katacoda/katacoda-jenkins-demo. The repository has a Dockerfile; this defines the instructions on how to produce the Docker Image. Jenkins doesn't need to know the details of how our project is built.
Task: Create New Job
	1. On the Jenkins dashboard, select Create new jobs
	2. Give the job a friendly name such as Katacoda Jenkins Demo, select Freestyle project then click OK.
	3. The build will depend on having access to Docker. Using the "Restrict where this project can be run" we can define the label we set of our configured Docker agent. The set "Label Expression" to docker-agent. You should have a configuration of "Label is serviced by no nodes and 1 cloud".
If you see the error message There’s no agent/cloud that matches this assignment. Did you mean ‘master’ instead of ‘docker-agent’?, then the Docker plugin and the Docker Agent has not been Enabled. Go back to configure the system options and enable both checkboxes.
	1. Select the Repository type as Git and set the Repository to be https://github.com/katacoda/katacoda-jenkins-demo.
	2. We can now add a new build step using the Add Build Step dropdown. Select Execute Shell.
	3. Because the logical of how to build is specified in our Dockerfile, Jenkins only needs to call build and specify a friendly name.
In this example, use the following commands.
Copy to Clipboardls
docker info
docker build -t katacoda/jenkins-demo:${BUILD_NUMBER} .
docker tag katacoda/jenkins-demo:${BUILD_NUMBER} katacoda/jenkins-demo:latest
docker images
The first stage lists all the files in the directory which will be built. When calling docker build we use the Jenkins build number as the image tag. This allows us to version our Docker Images. We also tag the build with latest.
At this point, or in an additional step, you could execute a docker push to upload the image to a centralised Docker Registry.
	1. Our build is now complete. Click Save.
```

### STEP5:
#### Build Project
```
We now have a configured job that will build Docker Images based on our Git repository. The next stage is to test and try it.
Task: Build
On the left-hand side, select Build Now. You should see a build scheduled with a message "(pending—Waiting for next available executor)".
In the background, Jenkins is launching the container and connecting to it via SSH. Sometimes this can take a while to configure the Docker Agent. The error "(pending—Jenkins doesn’t have label docker-agent)" is while Jenkins waits for the Docker Agent to start.
You can see the progress using docker logs --tail=10 jenkins
It's normal for this to take a few moments to complete.
```

### STEP6:
#### View Console Output
```
Once the build has completed you should see the Image and Tags using the Docker CLI docker images.
What was built into the Docker Image was a small HTTP server. You can launch it using: docker run -d -p 80:80 katacoda/jenkins-demo:latest
Using cURL you should see the server respond: curl host01
Jenkins will have the console output of our build, available via the dashboard. You should be able to access it below:
https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/job/Katacoda%20Jenkins%20Demo/1/console
If you rebuilt the project, you would see a version 2 image created and the :latest tag reattached.
```
---
## Tomcat Installation using Ansible Playbook role

##### https://computingforgeeks.com/install-tomcat-on-ubuntu-centos-with-ansible/
---
