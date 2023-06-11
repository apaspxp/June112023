pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Stage 1') {
            steps {
                echo 'Executing Stage 1'
                // Stage 1 steps
            }
            post {
                always {
                    input(
                        id: 'stage2',
                        message: 'Proceed to Stage 2?',
                        parameters: [
                            [$class: 'BooleanParameterDefinition', defaultValue: false, description: '', name: 'proceed']
                        ]
                    )
                }
            }
        }
        stage('Stage 2') {
            steps {
                echo 'Executing Stage 2'
                // Stage 2 steps
            }
            post {
                always {
                    input(
                        id: 'stage3',
                        message: 'Proceed to Stage 3?',
                        parameters: [
                            [$class: 'BooleanParameterDefinition', defaultValue: false, description: '', name: 'proceed']
                        ]
                    )
                }
            }
        }
        stage('Stage 3') {
            steps {
                echo 'Executing Stage 3'
                // Stage 3 steps
            }
            post {
                always {
                    input(
                        id: 'stage4',
                        message: 'Proceed to Stage 4?',
                        parameters: [
                            [$class: 'BooleanParameterDefinition', defaultValue: false, description: '', name: 'proceed']
                        ]
                    )
                }
            }
        }
        stage('Stage 4') {
            steps {
                echo 'Executing Stage 4'
                // Stage 4 steps
            }
        }
    }
}
