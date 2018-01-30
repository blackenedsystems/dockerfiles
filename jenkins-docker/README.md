Jenkins Docker
--------------

Adapted from: https://github.com/wardviaene/jenkins-docker

Builds an image from the LTS jenkins image, adding docker client packages to allow communication with the hosts docker installation.

Example build command:

docker build --tag blackened/jenkins-docker .

Example run command:

docker run --name jenkins-docker -p 8080:8080 -p 50000:50000 -v /var/jenkins_home:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock -d blackened/jenkins-docker

NB. make sure /var/jenkins_home has the correct access rights for the docker user, otherwise jenkins will fail to start.