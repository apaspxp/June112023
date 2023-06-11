pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Stage 1') {
            steps {
                echo 'Executing Stage 1'
                script {
                    def userInput = input(
                        id: 'stage2',
                        message: 'Proceed to Stage 2?',
                        parameters: [
                            [$class: 'StringParameterDefinition', defaultValue: '', description: 'Enter a value:', name: 'inputValue']
                        ]
                    )

                    if (userInput.inputValue == 'proceed') {
                        echo 'User chose to proceed to Stage 2'
                        env.CONTINUE_STAGE_2 = true
                    } else {
                        echo 'User chose not to proceed to Stage 2'
                        env.CONTINUE_STAGE_2 = false
                    }
                }
            }
            post {
                always {
                    script {
                        if (env.CONTINUE_STAGE_2 == true) {
                            echo 'Proceeding to Stage 2'
                            build 'Stage 2'
                        } else {
                            echo 'Skipping Stage 2'
                        }
                    }
                }
            }
        }

        stage('Stage 2') {
            steps {
                echo 'Executing Stage 2'
                script {
                    def userInput = input(
                        id: 'stage3',
                        message: 'Proceed to Stage 3?',
                        parameters: [
                            [$class: 'StringParameterDefinition', defaultValue: '', description: 'Enter a value:', name: 'inputValue']
                        ]
                    )

                    if (userInput.inputValue == 'proceed') {
                        echo 'User chose to proceed to Stage 3'
                        env.CONTINUE_STAGE_3 = true
                    } else {
                        echo 'User chose not to proceed to Stage 3'
                        env.CONTINUE_STAGE_3 = false
                    }
                }
            }
            post {
                always {
                    script {
                        if (env.CONTINUE_STAGE_3 == true) {
                            echo 'Proceeding to Stage 3'
                            build 'Stage 3'
                        } else {
                            echo 'Skipping Stage 3'
                        }
                    }
                }
            }
        }
        stage('Stage 3') {
            steps {
                echo 'Executing Stage 3'
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
        stage('Stage 4') {
            steps {
                echo 'Executing Stage 4'\
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
        stage('Stage 5') {
            steps {
                echo 'Executing Stage 5'
            }
            post {
                always {
                    input(
                        id: 'stage4',
                        message: 'Proceed to Stage 5?',
                        parameters: [
                            [$class: 'BooleanParameterDefinition', defaultValue: false, description: '', name: 'proceed']
                        ]
                    )
                }
            }
        }
        stage('Stage 6') {
            steps {
                echo 'Executing Stage 6'
            }
        }
    }
}
