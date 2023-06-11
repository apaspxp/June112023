pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Hello world from Jenkinsfile!'
                echo "Change title is ${env.CHANGE_TITLE}"
                echo "Current build is ${currentBuild.number}"
                echo "Job name is ${env.JOB_NAME}"
            }
        }
    }
}

