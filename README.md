
# NGINX webserver that serves a simple page containing its hostname, IP address and port as wells as the request URI and the local time of the webserver.

Demo borrowed from https://github.com/nginxinc/NGINX-Demos
README WIP

The images are uploaded to Docker Hub -- https://hub.docker.com/r/stefsuse/nginx-hello/.

How to run:
```
$ docker run -P -d stefsuse/nginx-hello
```

K8S deploy:
```
$ cd hello-cf
$ helm install ./
```

Now, assuming we found out the IP address and the port that mapped to port 80 on the container, in a browser we can make a request to the webserver and get the page below: ![hello](hello.png)

A plain text version of the image is available to build. This version returns the same information in the plain text format:
```
$ curl <ip>:<port>
Server address: 172.17.0.2:80
Server name: 22becba5323d
Date: 07/Feb/2018:16:05:05 +0000
URI: /
Request ID: 48ba0db334a6ed165e783469c2af868f
```

The images were created to be used as simple backends for various load balancing demos.
 

Build Status   
[![Codefresh build status]( https://g.codefresh.io/api/badges/build?repoOwner=stefarnold&repoName=hello-cf&branch=master&pipelineName=all-the-things&accountName=stefarnold&type=cf-1)]( https://g.codefresh.io/repositories/stefarnold/hello-cf/builds?filter=trigger:build;branch:master;service:5af36ff6b1d7540001731bec~all-the-things)


