pipeline {
    agent any
    tools {
        maven 'Maven 3.8.1'
        jdk 'openjdk 8-jdk'
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }

        stage ('Build') {
            steps {
                sh 'mvn clean package' 
            }
        }
    }
}
