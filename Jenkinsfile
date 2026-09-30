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
                sh 'docker compose version'
            }
        }


        stage('Validate Docker Compose') {
            steps {
                sh 'docker compose config'
            }
        }


        stage('Start Services') {
            steps {
                sh 'docker compose up -d'
            }
        }


        stage('Check Running Containers') {
            steps {
                sh 'docker ps'
            }
        }


        stage('Cleanup') {
            steps {
                sh 'docker compose down'
            }
        }

    }


    post {
        always {
            echo 'Docker Compose CI Pipeline completed'
        }
    }
}
