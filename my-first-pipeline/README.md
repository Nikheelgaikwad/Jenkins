# A simple jenkins pipeline to verify if the docker slave configuration is working as expected.

# we have installed jenkins and docker on same container to avoid cost optimization so not that we dont have to depend on VM or ec2 instance for node configiration or agent now we can docker as agent by using this image
#image
nikhilgaikwad3196/jenkins-with-docker:latest (pull this image from docker hub)
#steps to run this 
docker build -t nikhilgaikwad3196/jenkins-with-docker .
docker run -d \
  -p 8080:8080 \
  -p 50000:50000 \
  -v <local_path>:/var/jenkins_home \
  -v /var/run/docker.sock:/var/run/docker.sock \
  jenkins-with-docker

 
