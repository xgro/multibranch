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
                echo "DEPLOY_TO: ${DEPLOY_TO}"
            }
        }
    }
}