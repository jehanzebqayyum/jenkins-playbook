1- install jenkins
2- create git repo
3- create pipeline

just mention github username and it'll pull public repos
no need for credentials


got docker: not found error
solution:
http://jpetazzo.github.io/2015/09/03/do-not-use-docker-in-docker-for-ci/

http://container-solutions.com/running-docker-in-jenkins-in-docker/



list containers
>docker ps

stop container
>docker stop [container name]


rerun with docker socket mapped to docker (so that jenkins can start sibling docker containers)

docker run -d -p 49001:8080 -v $PWD/jenkins:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock -v $(which docker):/usr/bin/docker -t jenkins
docker run -d -p 49001:8080 -v $PWD/jenkins:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock jenkins-docker

