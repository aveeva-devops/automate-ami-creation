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



