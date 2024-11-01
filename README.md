# Launch-App-Using-EFS-and-VPC
We first setup a profile and region so we can build the application and then create a VPC with a CIDR block range and set the instance tenancy. We also add a tag to the VPC and the secret/access keys.

Next, we create a public subnet in the VPC and specify the availability zone and attach a internet gateway to the public subnet so the website can be accessible. We create a route table for the VPC and and associate it with the public subnet. 

We create a security group with inbound rules to allow port 22 and 80 for SSH and HTTP access and port 2049 for EFS access. 

We launch an instance attached to the previously made security group 

We then create an EFS storage and attach the security group and subnet where the application is running 

We then mount the EFS storage to a folder so the data from the application stays persistent even if the instance goes down. 

Next, we create an S3 bucket to make it publically readable and store images in the bucket.

Finally, we create an Cloudfront to reduce latency. We set the time to live and set the cache behavior 
