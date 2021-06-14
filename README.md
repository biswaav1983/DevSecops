
# DevSecOps_Interview_Questions
This repo contains latest interview questions for DevOpsDevSecOps interview

#DockerFile to create Jenkins Docker Contianer in Linux 

Step 1. docker network create jenkins
Step 2. docker run --name jenkins-docker --rm --detach   --privileged --network jenkins --network-alias docker --env DOCKER_TLS_CERTDIR=/certs  --volume jenkins-docker-certs:/certs/client --volume jenkins-data:/var/jenkins_home --publish 2376:2376 docker:dind --storage-driver overlay2

Step 3. docker build -t myjenkins-blueocean:1.1 .
Step 4. docker run --name jenkins-blueocean --rm --detach   --network jenkins --env DOCKER_HOST=tcp://docker:2376   --env DOCKER_CERT_PATH=/certs/client --env DOCKER_TLS_VERIFY=1   --publish 8080:8080 --publish 50000:50000   --volume jenkins-data:/var/jenkins_home   --volume jenkins-docker-certs:/certs/client:ro   myjenkins-blueocean:1.1



