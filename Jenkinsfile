pipeline {
    agent {
        docker {
            image 'maven:3.6.3-jdk-11'
            args '-v /root/.m2:/root/.m2'
        }
    }

    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build Project') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}