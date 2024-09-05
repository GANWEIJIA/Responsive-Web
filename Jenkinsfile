pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // This is where we fetch the code from the repository
                git branch: 'main', url: 'https://github.com/GANWEIJIA/Responsive-Web'
            }
        }
        stage('Build') {
            steps {
                // Build the project using Gradle wrapper
                powershell './gradlew.bat clean build'  
            }
        }
        stage('Test') {
            steps {
                // Run the tests
                powershell './gradlew.bat test'
            }
        }
    }

    post {
        always {
            echo 'Cleaning up workspace'
            deleteDir()
        }
    }
}
