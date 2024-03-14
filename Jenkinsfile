pipeline {
    
    agent any
    
    stages {
        
        
                  stage('Docker Build PHP') {
                steps {
                    sh 'cd jenkins7pm/php && sudo docker build -t phptst .'
                    sh 'sudo docker images'
                }
            }
            

                 stage('Docker Build MYSQL') {
                steps {
                    sh 'cd jenkins7pm/mysql && sudo docker build -t mysqltst .'
                    sh 'sudo docker images'
                }
            }


            stage('Push to Docker Hub PHP') {
                steps {
		   sh 'sudo docker image tag phptst susigugh/phptst:v1'
		    sh 'sudo docker login -u="susigugh" -p="Jumper@12345" && sudo docker push susigugh/phptst:v1'
                    sh 'echo "Image Pushed to Docker Hub"'
                }
            }

          stage('Push to Docker Hub MYSQL') {
                steps {
                   sh 'sudo docker image tag mysqltst susigugh/mysqltst:v1'
                    sh 'sudo docker login -u="susigugh" -p="Jumper@12345" && sudo docker push susigugh/mysqltst:v1'
                    sh 'echo "Image Pushed to Docker Hub"'
                }
            }
            
            stage('Deploy to Kubernetes') {
                steps {
                   sh 'echo "Deploying to Kubernetes"'
                }
            }
         
            
        }
    }

