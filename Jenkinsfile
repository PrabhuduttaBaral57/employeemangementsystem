
pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Java source code checked out'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn package'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar',
                                 followSymlinks: false
            }
        }
    }

    post {
        success {
            echo 'Java CI Pipeline completed successfully!'
        }

        failure {
            echo 'Java CI Pipeline failed!'
        }
    }
}
