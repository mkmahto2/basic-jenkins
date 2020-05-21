# Jenkins on docker 
First, pull the official jenkins image from Docker repository.
~~~
docker pull jenkins
~~~

Next, run a container using this image and map data directory from the container to the host; e.g in the example below /var/jenkins_home from the container is mapped to jenkins/ directory from the current path on the host. Jenkins 8080 port is also exposed to the host as 49001.

~~~
docker run -d -p 49001:8080 -v $PWD/jenkins:/var/jenkins_home:z -t jenkins/jenkins
~~~
