pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                // Clone the repository
                sh 'git clone https://github.com/NUCESFAST/scd-final-lab-exam-abdullaharif24.git'
            }
        }
        stage('Build Docker Images') {
            steps {
                // Build frontend Docker image
                dir('scd-final-lab-exam-abdullaharif24/1762_frontend_client') {
                    sh 'docker build -t frontend-image .'
                }

                // Build backend Docker images
                dir('scd-final-lab-exam-abdullaharif24/1762_backend_post') {
                    sh 'docker build -t post-image .'
                }

                dir('scd-final-lab-exam-abdullaharif24/1762_backend_classrooms') {
                    sh 'docker build -t classrooms-image .'
                }

                dir('scd-final-lab-exam-abdullaharif24/1762_backend_event_bus') {
                    sh 'docker build -t event-bus-image .'
                }

                dir('scd-final-lab-exam-abdullaharif24/1762_backend_auth') {
                    sh 'docker build -t auth-image .'
                }
            }
        }
        stage('Run Docker Containers') {
            steps {
                // Run frontend container
                sh 'docker run -d -p 1762:1762 frontend-image'

                // Run backend containers (adjust ports as needed)
                sh 'docker run -d -p 3000:3000 post-image'
                sh 'docker run -d -p 4000:4000 classrooms-image'
                sh 'docker run -d -p 5000:5000 event-bus-image'
                sh 'docker run -d -p 6000:6000 auth-image'
            }
        }
    }
}
