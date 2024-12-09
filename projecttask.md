
##Task Project
Create VPC with /16 range
![preview](images/pk1.png)
- Create IGW for VPC
![preview](images/pk3.png)
- Create Two Subnets
- Pub and Pvt
- Pub Should have 4k Ip's
- Pvt Should Have 256 Ip's
![preview](images/pk2.png)

- Create 3 servers across diff subnets. help me complete task 
![preview](images/pk4.png)
![preview](images/pk5.png)
- These servers are used for running application
- Create a DB - using RDS

- CODE For the Project - https://github.com/Ai-TechNov/On-Premise-Deployement.git

- Create 3 ec2 instance across Pvt-Subnets
![preview](images/pk6.png)
![preview](images/pk7.0.png)
![preview](images/pk7.1.png)
![preview](images/pk7.2.png)
![preview](images/pk7.3.png)
![preview](images/pk7.4.png)

- Deploy Above mentioned python code on the ec2's

- Create and Integrate RDS - DB within the code across all the 3 ec2. 
![preview](images/pk7.5.png)
![preview](images/pk7.6.png)
![preview](images/pk7.7.png)
![preview](images/pk7.5.png)
![preview](images/pk7.6.png)
![preview](images/pk7.7.png)
- As the app is running on PVT, it should be accessible via www !!
- The DB should be purely Pvt, and access should remian strictly to the admin !!

- For the Above infra, i want load-balancing to be configured.
![preview](images/pk8.png)
![preview](images/pk9.png)
![preview](images/pk10.png)
![preview](images/pk11.png)
![preview](images/pk12.png)
![preview](images/pk13.png)
![preview](images/pk15.png)
![preview](images/pk16.png)
![preview](images/pk17.png)
![preview](images/pk18.png)
![preview](images/pk19.png)
![preview](images/pk20.png)
![preview](images/pk21.png)
![preview](images/pk22.png)
![preview](images/pk23.png)
![preview](images/pk24.jpg)
![preview](images/pk25.jpg)

- I want  Auto scaling for the 3 ec2's in order to avoid FT.
- These instances should be monitored and notificaitons should be in place !!

- Finally, The routing should happen via, ROUTE-53 using a Custom domain !

- IF any users browses the CDN, it should reach to app, where the app should collect user info and store it to the DB.
But, i want all the infra to be deployed in pvt-resources !! 

