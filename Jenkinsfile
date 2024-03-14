pipeline {
    
    agent any
    
    stages {
        
        
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

