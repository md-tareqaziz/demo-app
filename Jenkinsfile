node{
   stage('Mvn Package'){
     def mvnCMD = "/usr/share/maven/bin/"
     sh "${mvnCMD}mvn clean package"
   }
   stage('Build Docker Image'){
     sh 'docker build -t tq36/demo-app:2.0.0 .'
   }
}
