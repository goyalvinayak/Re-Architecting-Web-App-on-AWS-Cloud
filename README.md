# Re-Architecting Web App on AWS Cloud
## Contents
* [Introduction](#Introduction "Goto Introduction")
* [AWS Services Used](#AWS-Services-Used "Goto AWS Services Used")

## Introduction
Re-Architecting or re-factoring of multi tier web application to boost agility or improve business continuity.

## AWS Services Used
### Services
* Beanstalk- Instead of Tomcat on EC2 
* ELB in Beanstalk- Instead of NGINX LB
* Autoscaling
* EFS/S3
* RDS- Instead of MySQL on EC2
* Elastic Cache- Instead of Memecached on EC2
* Active MQ- Instead of RabbitMQ on EC2
* Route53
* Cloudfront
### Architecture
![Screenshot (21)](https://github.com/user-attachments/assets/049df373-2abc-4deb-9352-6172d357632f)
### Flow of execution
1. Login to AWS Account
2. Create Key Pair for Beanstalk instance login
3. Create Security Group for ElasticCache, RDS and Active MQ
4. Create
   * RDS
   * Amazon Elastic Cache
   * Amazon Active MQ
5. Create Elastic Beanstalk Environment
6. Update SG of backend to allow traffic from Bean SG
7. Update SG of backend to allow internal traffic
8. Launch an EC2 instance for DB-Initializing
9. Login to theh instance and initialize RDS DB
10. Change healthcheck on beanstalk to/login
11. Add 443 https listner to ELB
12. Build artifact with Backend Information
13. Deploy artifact to beanstalk
14. Test the URL
