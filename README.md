# Test case to reproduce the issue

To reproduce the issue, follow these steps:

* Clone this repository to your local machine

* Open a shell and navigate to the cloned repository

* Set the following environment variables to hold your Docker Hub user name and password. 
``` bash
export X_USERNAME=<dockerhub-username>
export X_PASSWORD=<dockerhub-password>
```
* Run the pipeline2 pipeline directly (works)

```
wercker build --pipeline pipeline2
```

This successfully builds an image and pushes it to Docker Hub.

* Run the pipeline2 pipeline as part of a workflow (fails)

```
wercker workflow all
```

The `docker-push` step fails with

```
Pushing image built using internal/docker-build step, image name: my-new-image
Pushing image for  docker.io/nigeldeakin/push-issue:latest
The push refers to repository [docker.io/nigeldeakin/push-issue]
Preparing: b14c5f5e7314
...
Waiting: f36835e80d44
denied: requested access to the resource is denied
--> denied: requested access to the resource is denied
--> Step failed: docker push denied: requested access to the resource is denied 1.28s
--> Pipeline failed: 39.05s
FATAL Unable to run workflow: unable to run pipeline pipeline2: Step failed: docker push
```
