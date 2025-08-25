pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main',
                credentialsId: 'git',
                url: 'git@github.com:tanyongding/jenkins.git'
            }
        }
        stage('Read File') {
            steps {
                sh 'cat file.txt'
            }
        }
        stage('Build Information') {
            steps {
                sh '''
                    echo "Build Number: $BUILD_NUMBER"
                    echo "Build ID: $BUILD_ID"
                    echo "Job Name: $JOB_NAME"
                '''
            }
        }
    }
    post {
        always {
            echo "Pipeline completed - Status: $currentBuild.result"
        }
        success {
            echo "Pipeline succeeded! 🎉"
        }
        failure {
            echo "Pipeline failed! ❌"
        }
    }
}
