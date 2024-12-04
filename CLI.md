

- 
![preview](images/clitask1.png)
Create VPC using cli
 aws ec2 create-vpc --cidr-block 10.0.0.0/16
 ![preview](images/clitask2.png)

- create Pub and Pvt subnets
      pub==> subnet-04dc907c1e5ba327eaws ec2 create-subnet --vpc-id <vpc-id> --cidr-block 10.0.1.0/24 --availability-zone

      >aws ec2 create-tags --resources subnet-0aeab581fb7f6d1f2 --tags Key=Name,Value=Pub-cli

     ![preview](images/clitask3.png)
       pvt==>subnet-040773d6373797026
      
      - create IGW
      aws ec2 create-internet-gateway
![preview](images/clitask4.png)
- Attach IGW to VPC

    aws ec2 attach-internet-gateway --vpc-id <vpc-id> --internet-gateway-id <igw-id>

- Create Pub and PVT RT
  aws ec2 create-route-table --vpc-id <vpc-id>
        
- Attach Pub sub to Pub rt
   aws ec2 associate-route-table --route-table-id <public-rt-id> --subnet-id <public-subnet-id>  

- Attach Pvt Sub to Pvt rt
![preview](images/clitask5.png)


- Create Sg for ssh
Allow Http Access Port 22

aws ec2 authorize-security-group-ingress --group-id sg-01c23eec36f8fda03 --protocol tcp --port 22 --cidr 0.0.0.0/0

Allow Http Access Port 80
 aws ec2 authorize-security-group-ingress --group-id sg-01c23eec36f8fda03 --protocol tcp --port 80 --cidr 0.0.0.0/0

- Create a Ec2 in Pub Sub
aws ec2 run-instances --image-id ami-0dee22c13ea7a9a67  --instance-type t2.micro --key-name demo --subnet-id subnet-04dc907c1e5ba327e --security-group-ids sg-01c23eec36f8fda03

Ec2 Name Creation >aws ec2 create-tags --resources i-075b054106cc52520 --tags Key=Name,Value=MyC2Instance 
- Create a Ec2 in Pvt Sub 
![preview](images/clitask6.png)
aws ec2 authorize-security-group-ingress --group-id <sg-id> --protocol tcp --port 22 --cidr 0.0.0.0/0
aws ec2 authorize-security-group-ingress --group-id <sg-id> --protocol tcp --port 80 --cidr 0.0.0.0/0

- Create a Ec2 in Pvt Sub 
aws ec2 create-security-group --group-name PrivateSG --description "Private SG" --vpc-id <vpc-id>
>aws ec2 run-instances --image-id ami-0dee22c13ea7a9a67  --instance-type t2.micro --key-name demo --subnet-id subnet-040773d637379702
6 --security-group-ids sg-01c23eec36f8fda03
aws ec2 create-security-group --group-name PrivateSG --description "Private SG" --vpc-id <vpc-id>

![preview](images/clitask7.png)
![preview](images/clitask8.png)
