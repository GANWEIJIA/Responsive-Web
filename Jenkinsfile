pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/GANWEIJIA/Responsive-Web'
            }
        }
        stage('Build') {
            steps {
                powershell './gradlew.bat clean build'  // Use gradlew.bat for Windows
            }
        }
        stage('Test') {
            steps {
                powershell './gradlew.bat test'  // Use gradlew.bat for Windows
            }
        }
    }

    post {
        always {
            echo 'Cleaning up workspace'
            deleteDir()
        }
        success {
            echo 'Build and tests successful!'
        }
        failure {
            echo 'Build or tests failed.'
        }
    }
}
