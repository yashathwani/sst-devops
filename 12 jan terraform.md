12 jan terraform

more terraform today. this time with aws networking stuff.

subnets:
- private subnet: no internet access. cant reach it from outside.
- public subnet: connected to internet gateway. accessible from outside.
- terraform figures out dependencies automatically. if u reference a resource in another block it knows what to create first.

vpc (virtual private cloud):
- ur own virtual network in aws. isolated from everyone else.
- cidr block: defines the ip range for ur vpc. like 10.0.0.0/16.
- routing tables: rules for where traffic goes based on destination ip.

terraform state:
- terraform.tfstate file tracks what infra u have.
- if multiple ppl working on same infra use remote state. put it on s3.
- use dynamodb for state locking so ppl dont mess each other up.

common tf files:
- main.tf: main config.
- network.tf: vpc, subnets, internet gateway.
- compute.tf: ec2, security groups.

ip types in aws:
- private ip: only works inside vpc.
- public ip: reachable from internet.
- elastic ip: static public ip that sticks to ur account. can move it around.

ec2 stuff:
- u need an ami to launch an instance. no ami = no ec2.
- ami is like a template with the os and stuff.

variables in terraform:
- input vars: make ur config flexible.
- output vars: show info about ur infra after apply.
- local vars: only for that one file.

summary:
today was about how terraform works with aws networking. vpc, subnets, state files, and variables.
