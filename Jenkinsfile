pipeline {

    agent {
        label 'docker-agent'
    }

    stages {

        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }


        stage('Docker Version Check') {
            steps {
                sh 'docker --version'
            }
        }


        stage('Build Docker Agent Image') {
            steps {
                sh 'docker build -t test-docker-agent -f Dockerfile.agent .'
            }
        }


        stage('Test Docker') {
            steps {
                sh 'docker run --rm hello-world'
            }
        }

    }


    post {

        success {
            echo 'CI Pipeline completed successfully'
        }

        failure {
            echo 'CI Pipeline failed'
        }

    }
}
