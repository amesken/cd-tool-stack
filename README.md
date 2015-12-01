# CI/CD Tools Demo

This GitHub repository contains Dockerfiles for running a set of Continuous Integration/Delivery Tools with a single command.
The diagram contains all tools used in the Docker containers.

![Docker CD Tools](screenshots/docker-cd-tools.png)

## Prerequisites (Mac)

You should have Docker Toolbox installed, see https://www.docker.com/toolbox

I am using docker-compose to start several docker container at once.
Since all containers run in a single VM (virtualbox), this VM needs enough memory.

### Step 0 - List Docker Machine

```
~/git/docker-cd-tool-stack$ docker-machine ls

NAME      ACTIVE   DRIVER       STATE     URL                         SWARM
default   *        virtualbox   Running   tcp://192.168.99.100:2376
```

### Step 1 - Stop your docker VM

```
docker-machine stop default
```

### Step 2 - Increase Memory via VirtualBox UI

I am using 6000MB for my VM.

![VirtualBox](screenshots/virtualbox.png)

### Step 3 - Start VM

```
docker-machine start default
```

## Getting started

To get all docker containers up and running use:

```
git clone git@github.com:amesken/cd-tool-stack.git
cd cd-tool-stack
docker-compose up
```

## Access Tools

| *Tool* | *Link* | *Credentials* |
| ------------- | ------------- | ------------- |
| Jenkins | http://${docker-machine ip default}:18080/jenkins/ | no login required |
| SonarQube | http://${docker-machine ip default}:19000/ | admin/admin |
| Artifactory | http://${docker-machine ip default}:18081/artifactory | admin/password |
| GitLab | http://${docker-machine ip default}:10080/ | root/5iveL!fe |
| Selenium Grid | http://${docker-machine ip default}:4444/grid/console | no login required |

## Screenshots

Here is an overview of all tools:

- GitLab is used for storing the Sourcecode
- Jenkins contains build job and is triggered once projects in GitLab are updated
- As part of the CI build, Jenkins triggers a static code analysis and the results are stored in SonarQube
- The Maven build uses Artifactory as a Proxy Repository for all 3rd party libs. The build artefacts are deployed to the Artifactory Release Repository
- The Selenium Grid contains Docker containers running Chrome and Firefox and is used for UI tests

### Jenkins Jobs

There are several jobs preconfigured in Jenkins.
The Jobs cover the following tasks:

- Continuous Integration Build with Maven
- Unit Tests
- Static Source Analysis results are stored in SonarQube
- JaCoCo Test Coverage
- Deployment to Artifactory
- Jenkins Job DSL examples
- Selenium UI Test

![Conference App Jobs](screenshots/jenkins-jobs-1.png)

![Conference App CI Job](screenshots/jenkins-jobs-2-conference-app-ci.png)

### SonarQube Dashboard

![Jenkins Jobs](screenshots/sonar-analysis-conference-app.png)

### Artifactory Repository

![Artifactory Proxy Repository](screenshots/artifactory.png)

### Selenium Grid

![Selenium Grid](screenshots/selenium-grid.png)
