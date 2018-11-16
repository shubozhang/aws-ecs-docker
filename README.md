# aws-ecs-docker

### AWS ECS
### Docker Basics
### ECS Container Instances
### ECS-Wroking With Cluster
### ECS with Jenkins

### 1. AWS ECS
* Easily manage clusters of any scale
* Flexible container placement
* Integrates with other AWS services
* Extensible



AWS ECS features:
* Container and Images
* Task Definition
* AutoScaling
* Security Groups
* Elastic Load Balancing
* EBS volumbs
* IAM Roles

AWS ECS components
* AWS Container EC2 Instances
* Run As Docker Daemon
* Run AWS ECS Container Agent
* AWS ECS Cluster
* Resource Pool
* Scale Dynamiclly
* Task Definition
  ```json
    { "family": "webserver",
      "containerDefinition": [
        { "name":"web",
          "image":"ngix",
          "portMappings":[
            "container":80,
            "host":80
          ]
        }
      ]
    }
  ```
  * Related Services
    * AWS IAM
    * Auto Scaling (scale out / in)
    * Elastic Load Balancing (traffic distribution)
    * Amazon EC2 Container Registry(ECR)

### 2. Docker Basics
* Intro to docker
* Installation and configuration of docker
* AWS EC2 container registry

* Connect to AWS EC2 instance vis Putty:
  * Use PuttyGen to generate private ppk 
  * Import ppk to putty session
  * Start putty session
  * link: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html?icmpid=docs_ec2_console
  
  
* Docker Basics 
 ```
To install Docker on an Amazon Linux instance:
1) Connect: ssh -i key.pem username@ip-address/hostname
2) Update Installed Package: $sudo yum update -y
3) Install Docker:	$sudo yum install -y docker
4) Start the Docker service:	$sudo service docker start
5) Add the ec2-user to the docker group :	$sudo usermod -a -G docker ec2-user 
   // then restart session
6) $docker info
======================== Already Done in Previous Session ===================================================
7) Install git:	$sudo yum install -y git
8) Clone the simple PHP application:	$git clone https://github.com/awslabs/ecs-demo-php-simple-app
9) Change directories:	$cd ecs-demo-php-simple-app
10) Examine the Dockerfile:	$Cat Dockerfile
11) Build your Docker image:	$docker build -t bryan .
    i) Ignore the message "apache2: Cound not reliably determine the server's fully qualified domain name"
12) Show Docker images:	$docker images
13) Run the newly built image:	$docker run -p 80:80 bryan
14) Test app
    i) Allow access to port 80 of EC2 instance. Edit the Security Group -> Add inbound http.
    ii) Get ec2 instance public IP: IPv4 Public IP
    iii) In browser, for example, 100.11.10.170:80
15) After the build completes, tag your image:	
    $docker tag tetranoodle:latest 133976391764.dkr.ecr.us-east-1.amazonaws.com/bryan:latest 
16) Run the following command to push this image 
    i) Copy aws access to ec2 instance ~/.aws/config
    ii) $aws ecr get-login --region us-east-1 --no-include-email
    iii) Copy the return from ii) and run it
    iv) $docker push 133976391764.dkr.ecr.us-east-1.amazonaws.com/bryan:latest
 ```
