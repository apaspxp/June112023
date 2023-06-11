pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Hello world from Jenkinsfile!'
                echo "Branch name is ${env.BUILD_NUMBER}"
                echo "Current build is ${currentBuild.number}"
            }
        }
    }
}

