# DevOps Pipeline Project

Spring Boot REST API with a Jenkins CI pipeline and Ansible/Kubernetes deployment examples.

## Application

The service listens on port `8081` and exposes:

- `GET /api/hello`
- `GET /api/info`
- `GET /api/status`
- `GET /actuator/health`

Build the version 1.1 package with `mvn clean package` (or `./mvnw clean package` on Unix-like systems).

## Jenkins

The `Jenkinsfile` runs the test and package stages, then archives the JAR. Configure a Jenkins Pipeline job as **Pipeline script from SCM**, point it at this repository and the `main` branch, and use `Jenkinsfile` as the script path. The Jenkins tool configuration must provide tools named `JDK17` and `Maven3`.

The pipeline polls SCM every five minutes (`H/5 * * * *`) and starts a build when it detects a new commit. Jenkins must be able to access the configured repository. The polling schedule takes effect after Jenkins has loaded the pipeline definition.

## Deployment

The Ansible role and Docker/Kubernetes examples use application version `1.1`. Build the JAR before building the Docker image or running the Ansible deployment.
