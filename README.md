# fargate-cloudformation-example

An example CloudFormation template that deploys a container to AWS Fargate as a service.

Multiple AZs are used for high availability, SSL is terminated at the load balancer, health checks are used, a DNS record is created, and it scales to keep CPU utilization at or below 50%. Specifically, it includes:

* A cluster
* A task definition for the container
* An ECS service
* A load balancer and its associated listener and target group
* The necessary IAM roles
* Logging to CloudWatch Logs, including the creation of a log group
* Security groups for the container and load balancer
* A DNS record for Route 53
* An auto scaling policy

Was taken from https://github.com/1Strategy/fargate-cloudformation-example

The original template was left as it is in the root folder and a few more templates were added in the AA folder.
AA\Existing VPC\HTTPS\fargate.yaml by default uses alytic.io SSL certificate from London region and
AA\Create VPC\HTTPS\fargate.yaml uses the same alytic.io certificate from N. Virginia region so default certificate ARNs are valid in these regions.
