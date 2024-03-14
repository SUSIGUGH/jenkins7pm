pipeline {
    
    agent any
    
    stages {
        
        stage("Git Pull") {
            steps {
                sh 'rm -Rf jenkins7pm'
                sh 'git clone https://github.com/SUSIGUGH/jenkins7pm.git'
                sh 'ls -ltr'
                sh 'ls -ltr jenkins7pm/'
            }
        }
        
                  stage('Docker Build') {
                steps {
                    sh 'cd jenkins7pm/php && sudo docker build -t phptst .'
                    sh 'sudo docker images'
                }
            }
            
            stage('Push to Docker Hub') {
                steps {
                    sh 'echo "Docker Push"'
                }
            }
            
            stage('Deploy to Kubernetes') {
                steps {
                   sh 'echo "Deploying to Kubernetes"'
                }
            }
         
            
        }
    }

