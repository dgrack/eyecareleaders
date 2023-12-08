**Simple Apache Installation on AWS EC2 Cluster Placed Under Autoscaling**

**A. Goal** 

1. To spin up an EC2 cluster with Apache server pre-installed, that is placed under an AutoScaling Group and a Load Balancer.
2. Test the auto-scaling action by running a stress test on ec2 servers. 

**B. Prerequisites on your local CLI**

1. Install Terraform
2. Install TFSwitch
3. Install AWS CLI
4. Setup AWS CLI credentials. You'll also need AWS Management Console credentials for validation.

**C. How to spin-up this cluster**

1. Clone this repo on your local system
2. Run 'terraform init'
3. Run 'terraform plan'
4. Run 'terraform apply'
5. Login to AWS Management Console
6. Go to EC2 > LoadBalancer section and run the load balancer public URL in your browser. You should see this message "Hello world from highly available group of ec2 instances"

**D. To test the autoscaling action, here's how you can run a small stress test on any ec2 machine**

1. Login to any EC2 machine via AWS Systems Manager console
2. Run 'sudo apt install -y stress'
3. Run 'stress --version'
4. Run 'sudo stress --cpu 200 --timeout 10'
* '--cpu 200' means 200 hogs running together to stress the CPU. You may increase this number of hogs to put more stress on the cpu.
* On the AWS console, the autoscaling activity should start
6. Run 'ctrl+c' to exit

**E. Architectural Diagram is as follows**

![diagram](https://github.com/dgrack/eyecareleaders/assets/75610814/b9890048-15cb-471e-91af-4d8cf53d09f1)

