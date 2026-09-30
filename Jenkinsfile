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


        stage('Compose Validation Complete') {
            steps {
                echo 'Docker Compose configuration validated successfully'
            }
        }

    }


    post {
        always {
            echo 'Docker Compose CI Pipeline completed'
        }
    }
}
