/* groovylint-disable-next-line CompileStatic */
pipeline {
    // environment {
    //     registry = "https://docker.okit.in/"
    //     registryCredential = 'docker-hub-credentials'
    //     dockerImage = ''
    // }
    agent any
    stages {
        stage('Building Image') {
            steps {
               sh "docker-compose build --no-cache"
            }
        }
        stage('Deleting Old Container') {
            steps {
               sh "docker-compose down"             
            }
        }
        stage('Launching Container') {
            steps {
               sh "docker-compose up -d"
            }
        }
        stage('Cleaning Containers') {
            steps {
               sh "docker image prune -f"
               sh "docker system prune -a"
            }
        }
    }
}
