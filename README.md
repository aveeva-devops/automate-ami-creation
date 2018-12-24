# devops

This repo will help to build an immutable AWS AMI with Packer.
Create an identical machine image from a single source

### Steps

* Github setup  - https://github.com/
* Setup Jenkins master slave on docker - https://www.youtube.com/watch?v=Xl4miqBWkEk&t=1s 
* Integrate Github with Jenkins
* Create AMI using packer + ansible
* Use that AMI to create EC2 servers using Terraform

### Automation Workflow:
CI CD EC2 creation

![Alt text](packer_workflow.PNG?raw=true "Title")

### Step 1: GITHUB + Jenkins Integration

* Create Public Facing Jenkins Server using - https://www.youtube.com/watch?v=Xl4miqBWkEk&t=16s
* Install GITHUB integration plugin 
* Create a new Jenkins Job
* Create GitHub Webhook 
* Commit in repo and demo


![Alt text](GitHub-Jenkins-Integration.png?raw=true "Title")


### Step 2: Create docker Jenkins Slave for devOps activities
Container will have below softwares:
* packer - to create aws ami's
* terraform - to launch and configure aws resources
* ansible - to Configure and install software on servers
* git client - to interact with Github
* AWS CLI

Login on Jenkins Slave machine, and execute below commands to create docker image:

```
git clone https://github.com/aveeva-devops/automate-ami-creation.git
cd src/packer-docker-slave/
docker build -t aveevadevops/jenkins:devops_image .
docker login
docker push aveevadevops/jenkins:devops_image
```

Above steps will create image from Dockerfile, push it to docker hub.
Now, image is ready to be used as Jenkins slave

Once image is created, use this image to launch Jenkins slave (https://www.youtube.com/watch?v=Xl4miqBWkEk)
