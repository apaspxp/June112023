pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Hello world from Jenkinsfile!'
                echo "Branch name is env.BRANCH_NAME"
                echo "Current build is ${currentBuild.number}"
            }
        }
    }
}

