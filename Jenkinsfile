pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Build') {
            steps {
                sh 'echo Hello world from Jenkinsfile of first-branch!'
                sh "echo first-branch Change title is ${env.CHANGE_TITLE}"
                sh "echo first-branch Current build is ${currentBuild.number}"
                sh "echo first-branch Job name is ${env.JOB_NAME}"
                sh "echo first-branch Build duration ${currentBuild.durationString}"
            }
        }
    }
}

