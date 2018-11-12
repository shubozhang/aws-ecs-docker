# aws-ecs-docker

### AWS ECS
### Docker Basics
### ECS Container Instances
### ECS-Wroking With Cluster
### ECS with Jenkins

### AWS ECS
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

### Docker Basics
* Intro to docker
* Installation and configuration of docker
* AWS EC2 container registry

* Connect to AWS EC2 instance vis Putty:
  * Use PuttyGen to generate private ppk 
  * Import ppk to putty session
  * Start putty session
  * link: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/putty.html?icmpid=docs_ec2_console
