pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /root/.m2:/root/.m2'
        }
    }
    tools {
            maven 'maven:3-alpine'
            jdk 'jdk8'
        }
    stages {
        stage('Build') {
            steps {
                sh 'mvn spring-boot:build-image'
            }
        }
    }
}