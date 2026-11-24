pipeline {
    agent any

    tools {
        maven 'Maven3'
    }

    triggers {
        githubPush()
    }

    stages {

        stage('Build') {
            steps {
                echo 'Building Maven application...'
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'mvn test'
            }
        }

        stage('Package') {
            steps {
                echo 'Packaging application...'
                bat 'mvn package'
            }
        }
    }

    post {
        success {
            echo 'BUILD SUCCESSFUL!'
        }
        failure {
            echo 'BUILD FAILED!'
        }
    }
}
