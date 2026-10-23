pipeline {
    agent any

    stages {
        stage("Install Node modules") {
            steps {
                bat 'npm install'
            }
        }

        stage("Run Tests") {
            steps {
                echo 'Running Tests'
                bat 'npm test'
            }
        }

        stage("Deploy") {
            steps {
                withCredentials([
                    string(
                        credentialsId: 'render-deploy-hook',
                        variable: 'RENDER_DEPLOY_HOOK'
                    )
                ]) {
                    bat '''
                        @echo off
                        curl.exe -fsS -X POST "%RENDER_DEPLOY_HOOK%"
                    '''
                }
            }
        }
    }
}
