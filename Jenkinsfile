pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'maven:3.9.9-eclipse-temurin-21-alpine'
                    args '-u root'
                }
            }
            steps {
                checkout scm
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            agent {
                docker {
                    image 'node:22.13.1-alpine3.21'
                    args '-u root'
                }
            }
            steps {
                checkout scm
                sh 'npm test'
            }
        }
    }
}
