pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Simulate build failure for testing
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
    post {
        always {
            emailext(
                to: 'siddhant.satra@gmail.com',
                subject: "Build ${currentBuild.fullDisplayName} - ${currentBuild.result}",
                body: """
                    Build details:
                    - Job: ${env.JOB_NAME}
                    - Build Number: ${env.BUILD_NUMBER}
                    - Status: ${currentBuild.result}
                    - View the build log: ${env.BUILD_URL}
                """
            )
        }
    }
}
