## step 1 : create ubuntu ec2 instance in aws
## step 2 : install docker
## step 3 : create folder tomcat in /home
![image](https://user-images.githubusercontent.com/44174633/193208715-de59f110-7198-4163-a5af-c42dd6b6a4c1.png)

## step 4 : add Dockerfile, context.xml , tomcat-user.xml and sample.war file which we want to deploy and test in /tomcat folder
![image](https://user-images.githubusercontent.com/44174633/193209118-c8cf5226-8dcb-499e-8c56-3b5dfc34d74e.png)

Note: we have update context.xml for path webapps/META-INF/
commented following code and this file we are replacing when we run Dockerfile.
![image](https://user-images.githubusercontent.com/44174633/193212846-9807318e-0a5a-47b2-9d8a-fd1417cdd114.png)
Dockerfile
![image](https://user-images.githubusercontent.com/44174633/193213457-b40b3074-749e-44cc-adfc-ff0b3b577bf4.png)

Note: adding username and password in tomcat-user.xml
![image](https://user-images.githubusercontent.com/44174633/193213653-95f52c97-1ec9-409c-b334-82a49de1f2e2.png)
dockerfile
![image](https://user-images.githubusercontent.com/44174633/193213749-8ad81ddd-e607-4d5d-8ae8-7731d34e4fac.png)

## step 5 : now build docker image from Dockerfile 
* docker build -t (name of docker image which we want to create) .

## step 6 : once image build successfully then create container from it 
* docker run -p 8888:8080 --name (name of container) (name of existig image)

## step 7 : check container is running successfully
* docker ps or docker container ls -a
![image](https://user-images.githubusercontent.com/44174633/193210552-67c3f2b3-fafb-404b-9b74-fbdc8b34e61d.png)

## step7 : update inbound and outbound security group in aws
inbound
![image](https://user-images.githubusercontent.com/44174633/193210053-2093e5d4-55ad-4a9f-a4e6-600cfa41ae9e.png)
outbound
![image](https://user-images.githubusercontent.com/44174633/193210202-160f5fff-b62c-4b12-92d3-a9cbacf9879c.png)

# step 8: access tomcat on browser for this we have to use ipaddress from ec2 instance

![image](https://user-images.githubusercontent.com/44174633/193210817-03901bd7-221e-4ac8-9632-90dfdcc5f357.png)

## step 9: test springboot application
![image](https://user-images.githubusercontent.com/44174633/193211921-b5b05ee5-7fb8-4919-9013-7024b7094f1d.png)

Note: context path of spirngboot application and name of .war file should same .
![image](https://user-images.githubusercontent.com/44174633/193212344-9c46a9b6-f0f0-4d07-b825-a0702d6ae023.png)
![image](https://user-images.githubusercontent.com/44174633/193212530-63427668-7bc9-43f6-a2cf-a05c5ff8c101.png)




