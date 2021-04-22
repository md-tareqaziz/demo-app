pipeline {
    agent {
        docker {
            image 'git-maven:3-alpine'
            args '-v /root/.m2:/root/.m2 --network=host'
        }
    }

    parameters {
        string defaultValue: '', description: 'Release Version.', name: 'releaseVersion', trim: true
        string defaultValue: '', description: 'Next Devevelopment Version.', name: 'developmentVersion', trim: true
    }
    stages {
        stage('Checkout') {
            steps {
               checkout([$class: 'GitSCM',
						branches: [[name: 'origin/master']],
						doGenerateSubmoduleConfigurations: false,  extensions: [[$class: 'LocalBranch', localBranch: 'master']],
						submoduleCfg: [],
						userRemoteConfigs: [[credentialsId: 'yourCredsId', url: 'https://github.com/[username]/[project]']]])
            }
        }
        stage('Release') {
            steps {
                sh 'mvn release:clean release:prepare release:perform -DreleaseVersion=${releaseVersion} -DdevelopmentVersion=${developmentVersion}'
            }
        }
    }
}