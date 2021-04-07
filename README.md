# 1Click-HPC
This project aims at speeding up the deployment of an HPC Cluster. With just one click, a cluster will be started with the following AWS HPC services:
 * <b>AWS ParallelCluster</b> is an open source cluster management tool that simplifies deploying and managing HPC clusters.
 * <b>NICE EnginFrame</b> the leading HPC application portal for user-friendly submission,control and monitoring of batch jobs and interactive remote sessions.
 * <b>NICE DCV</b> a remote visualization technology that enables users to securely connect to graphic-intensive 3D applications hosted on a remote, high-performance server.
 * <b>Amazon FSx for Lustre</b> a fully managed service that provides cost-effective, high-performance, scalable storage for HPC workloads. 
 * <b>Elasit Fabric Adapter (EFA)</b> a network interface for Amazon EC2 instances that enables HPC applications requiring high levels of inter-node communications at scale on AWS.

# Architecture
![Architecture](docs/EnginFrame-1Click-Arch.png?raw=true "Architecture")

# Get Started
## Step 1
Click the link below corresponding to your preferred [AWS Region](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/) .

| Region       | Launch                                                                                                                                                                                                                                                                                                             | 
|--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| US  | --- |
| N. Virginia (us-east-1)   | [![Launch](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/us-east-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/quickcreate?templateUrl=https%3A%2F%2Fenginframe.s3.amazonaws.com%2FAWS-HPC-Cluster.yaml&stackName=hpc-cluster) |
| Ohio (us-east-2)   | [![Launch](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/us-east-2.svg)](https://console.aws.amazon.com/cloudformation/home?region=us-east-2#/stacks/quickcreate?templateUrl=https%3A%2F%2Fenginframe.s3.amazonaws.com%2FAWS-HPC-Cluster.yaml&stackName=hpc-cluster) |
| N. California (us-west-1)   | [![Launch](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/us-west-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=us-west-1#/stacks/quickcreate?templateUrl=https%3A%2F%2Fenginframe.s3.amazonaws.com%2FAWS-HPC-Cluster.yaml&stackName=hpc-cluster) |
| Oregon (us-west-2)   | [![Launch](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/us-west-2.svg)](https://console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks/quickcreate?templateUrl=https%3A%2F%2Fenginframe.s3.amazonaws.com%2FAWS-HPC-Cluster.yaml&stackName=hpc-cluster) |
| EU  |---|
| Frankfurt (eu-central-1)   | [![Launch](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/eu-central-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=eu-central-1#/stacks/quickcreate?templateUrl=https%3A%2F%2Fenginframe.s3.amazonaws.com%2FAWS-HPC-Cluster.yaml&stackName=hpc-cluster) |
| Ireland (eu-west-1)   | [![Launch](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/eu-west-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=eu-west-1#/stacks/quickcreate?templateUrl=https%3A%2F%2Fenginframe.s3.amazonaws.com%2FAWS-HPC-Cluster.yaml&stackName=hpc-cluster) |
| Stockholm (eu-north-1)   | [![Launch](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/eu-north-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=eu-north-1#/stacks/quickcreate?templateUrl=https%3A%2F%2Fenginframe.s3.amazonaws.com%2FAWS-HPC-Cluster.yaml&stackName=hpc-cluster) |
| APJ |---|
| Tokyo (ap-northeast-1)   | [![Launch](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/ap-northeast-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=ap-northeast-1#/stacks/quickcreate?templateUrl=https%3A%2F%2Fenginframe.s3.amazonaws.com%2FAWS-HPC-Cluster.yaml&stackName=hpc-cluster) |
| Hong Kong (ap-east-1)   | [![Launch](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/ap-east-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=ap-east-1#/stacks/quickcreate?templateUrl=https%3A%2F%2Fenginframe.s3.amazonaws.com%2FAWS-HPC-Cluster.yaml&stackName=hpc-cluster) |
| Mumbai (ap-south-1)   | [![Launch](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/ap-south-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=ap-south-1#/stacks/quickcreate?templateUrl=https%3A%2F%2Fenginframe.s3.amazonaws.com%2FAWS-HPC-Cluster.yaml&stackName=hpc-cluster) |


## Step 2
1. Just change the "Stack Name" as you like.
2. Enter the password for the Admin user "ec2-user":
2. Check the checkbox to acknowledge the IAM resources creations.
3. Click the "Create Stack" botton.
</br>

![Step2](docs/step2.png?raw=true "Step 2")

## Step 3
1. Click on the "Stack Name" to monitor the cluster creation steps.
2. Wait until all the resources are created 
</br>

![Step3](docs/step3.png?raw=true "Step 3")

## Step 4
1. When the cluster creation is completed, go to the "outputs" tab
2. Click the "EnginFrameURL" to access your HPC Cluster using the EnginFrame portal.
3. Alternatively, Click the "Cloud9URL" if you wish to connect to your Cloud9 Instance and then ssh into your cluster form there.
</br>

![Step4](docs/step4.png?raw=true "Step 4")

## Step 5
You can login on EnginFrame by using "ec2-user" as username and the password you chose.
```Username: ec2-user```
</br>
```Password: *********```
</br>

![Step5](docs/step5.png?raw=true "Step 5")

## Step 6
After you login, you are redirected to the "list Spoolers" page.
Spoolers are scratch area located in the /fsx FileSystem that are managed by EnginFrame and used as the HPC jobs execution directory.
</br>

![Step6](docs/step6.png?raw=true "Step 6")

## Step 7
We would reccomend to immediatelly change the password by using the service as below.
</br>

![Step7](docs/step7.png?raw=true "Step 7")


# Additional Docs

https://github.com/aws-samples/1click-hpc/tree/main/docs

# License

This software is licensed under the MIT-0 License. See the LICENSE file.