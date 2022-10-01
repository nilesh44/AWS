### step 1:place Dockerfile at location /home/mysql in the ec2-ubuntu.

### step 2 : create build from Docker file
* sudo docker build -t mysql:0.1 .

### step 3 : create and run container using build image
* docker run --detach --name=testmysql --publish 6603:3306 mysql:0.1

### remote login through mysqlwork bench , take public ip address from ec2-instance and password from Dockerfile.
![image](https://user-images.githubusercontent.com/44174633/193415873-6e62319f-8bc7-4e4a-b8f4-b1a6e70d042d.png)

Note: Always add configuration related to inbound and outbound in ec2-instance, for just practice we have make by default for all .

inbound
![image](https://user-images.githubusercontent.com/44174633/193415969-a2dadda9-d7c4-42c7-8a8a-8d9becadd338.png)
outbound
![image](https://user-images.githubusercontent.com/44174633/193415987-befe7518-37d4-4677-908b-95b6a87d6e1c.png)

