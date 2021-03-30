pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v $HOME/.m2:/root/.m2:z -u root'
        }
    }

    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build Project') {
            steps {
                sh 'clean package'
            }
        }
    }
}