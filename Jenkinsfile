pipeline {
    // "agent none" at top level lets each stage define its own container
    agent none

    stages {
        stage('Build') {
            agent {
                docker { image 'maven:3.9.9-eclipse-temurin-21-alpine' }
            }
            steps {
                sh 'mvn --version'
            }
        }

        stage('Test') {
            agent {
                docker { image 'node:22.13.1-alpine3.21' }
            }
            steps {
                sh 'node --eval "console.log(process.arch, process.platform)"'
            }
        }
    }
}
