# Test case to reproduce the issue

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
* Run the pipeline2 pipeline as part of a workflow (fails)

```
wercker workflow all
```
