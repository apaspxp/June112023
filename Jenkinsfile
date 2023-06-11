pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Hello world from Jenkinsfile!'
                echo 'Current build is ${currentBuild.number}'
            }
        }
    }
}

