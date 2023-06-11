pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Stage 0') {
            steps {
                sh 'echo Hello world from Jenkinsfile of first-branch!'
                sh "echo first-branch Change title is ${env.CHANGE_TITLE}"
                sh "echo first-branch Current build is ${currentBuild.number}"
                sh "echo first-branch Job name is ${env.JOB_NAME}"
                sh "echo first-branch Build duration ${currentBuild.durationString}"
            }
        }
        stage('Stage 1') {
            steps {
                sh "echo Step 1 of Stage 1"
            }
            post {
                always {
                    input("Proceed to Stage 2?", "Stage2")
                }
            }
        }
        stage('Stage 2') {
            steps {
                sh "echo Step 1 of Stage 2"
            }
            post {
                always {
                    input("Proceed to Stage 3?", "stage3")
                }
            }
        }
        stage('Stage 3') {
            steps {
                sh "echo Step 1 of Stage 3"
            }
            post {
                always {
                    input("Proceed to Stage 4?", "stage4")
                }
            }
        }
        stage('Stage 4') {
            steps {
                sh "echo Step 1 of Stage 4"
            }
        }
    }
}

