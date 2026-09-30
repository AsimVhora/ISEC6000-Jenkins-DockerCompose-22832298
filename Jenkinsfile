pipeline {

    agent {
        label 'docker-agent'
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Check Docker') {
            steps {
                sh 'docker --version'
            }
        }

        stage('Test Docker Container') {
            steps {
                sh 'docker pull hello-world'
                sh 'docker run hello-world'
            }
        }

    }

    post {

        success {
            echo 'Pipeline completed successfully'
        }

        failure {
            echo 'Pipeline failed'
        }

    }
}
