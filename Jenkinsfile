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
		   sh 'sudo docker image tag phptst susigugh/phptst:v1'
		    sh 'sudo docker login -u="susigugh" -p="Jumper@12345" && sudo docker push susigugh/phptst:v1'
                    sh 'echo "Image Pushed to Docker Hub'
                }
            }
            
            stage('Deploy to Kubernetes') {
                steps {
                   sh 'echo "Deploying to Kubernetes"'
                }
            }
         
            
        }
    }

