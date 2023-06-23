# Docker

===============================================================================================
#Installing docker
1) create a instance
2) sudo su –
3) sudo yum update –y
4) sudo yum install docker –y
5) service docker start
6) Add the ec2-user to the docker group so you can execute Docker commands without using sudo
    #usermod -a -G docker ec2-user

===============================================================================================
#basic commands:
1) docker pull centos
2) How to make container from Image
   docker run -it -d --name=myfirstcontainer centos
3) How to check running container’s
   #docker ps
4) docker images
5) How to login inside container:
   docker exec -it <container-id> bash
6) How to attach with a running container
   docker attach <container-id>
7) docker ps -a //is used to list all containers, including those that are currently running and those that have stopped.
8) docker stop <container-id>
9) docker start <container-id>
10) docker kill <container-id>
11) Login to hub.docker.com from command line #docker login

===================================================================================================
#Dockerfile

----------------
# Use a base Python image
FROM python:3.9

# Set the working directory
WORKDIR /app

# Copy the requirements file
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the application code
COPY . .

# Expose port 8000
EXPOSE 8000

# Set the command to run when the container starts
CMD ["python", "app.py"]
------------------------------------------------

to build a dockerfile 
docker build -t my-image:tag .


11) l
12) l
13) l



===========================================
common error:
Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock:
to solve following steps:
1) ls -ld /var/run/docker.sock
2) chmod 777 /var/run/docker.sock


=========================================
credential for docker hub:
secret text
type password


=======================================
ecr credentials in jenkins:'
create a user in iam
#create access keys and select third party service





