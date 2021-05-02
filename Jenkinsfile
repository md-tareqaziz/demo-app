pipeline{
    agent any
    stages{
       stage('Mvn Package'){
         def mvnHome = tool name: 'maven-3', type: 'maven'
         def mvnCMD = "/usr/share/maven/bin/"
         sh "${mvnCMD}mvn clean package"
       }
       stage('Build Docker Image'){
         sh 'docker build -t tq36/demo-app:2.0.0 .'
       }
    }
}
