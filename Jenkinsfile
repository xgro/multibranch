def DEPLOY_TO

pipeline {
    agent none
    stages {
        stage('Decide Deploy To') {
            steps {
                script {
                    if (env.BRANCH_NAME =~ 'main'){
                        DEPLOY_TO = 'prod'
                    } else if (env.BRANCH_NAME =~ 'dev'){
                        DEPLOY_TO = 'dev'
                    } else if (env.BRANCH_NAME =~ 'stag*'){
                        DEPLOY_TO = 'stag'
                    }
                }
            }
        }

        stage('ENV') {
            steps {
                echo "DEPLOY_TO: ${DEPLOY_TO}"
                echo "BUILD_ID: ${BUILD_ID}"
                echo "BUILD_NUMBER: ${BUILD_NUMBER}"
                echo "BUILD_TAG: ${BUILD_TAG}"
                echo "JOB_NAME: ${JOB_NAME}"
                echo "EXECUTOR_NUMBER: ${EXECUTOR_NUMBER}"
                echo "WORKSPACE: ${WORKSPACE}"
            }
        }
    }
}