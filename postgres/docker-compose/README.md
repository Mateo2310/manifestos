# Docker Compose

Project with some utils docker-compose files.

## Quick Start

Create a docker network to communicate your containers:

	docker network create common

Run docker containers with:

	docker-compose -f docker-compose-x.yaml up -d

### Sonar

Start the sonarqube interface

	docker-compose -f sonar/docker-compose-sonarqube.yaml up -d

Open localhost:9000 in your browser. For the first time you can access to sonarqube with:

    user: admin
    password: admin

Set a new password and then replace with this one the environment variable in **
sonar/docker-compose-sonar-scanner.yaml**

	environment:
      ...
      SONAR_PASSWORD: '<new-password>'

Put the file **sonar-project.properties** in the root path of your project to scan. You can change the project name that
sonarqube'll show in the **sonar.projectKey** property.

Scan your project with sonar-canner, run

	PROJECT_DIR=/path/to/your/project docker-compose -f sonar/docker-compose-sonar-scanner.yaml up
