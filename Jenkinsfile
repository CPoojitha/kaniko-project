pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
               
               bat 'mvn -Dmaven.test.failure.ignore=true clean package'
               }
               }
               
               
       stage('Building image') {
            steps{
                
          bat 'mvnw clean package -Dquarkus.container-image.build=true'
            }
            }
            stage('Deploying into k8s'){
            steps{
                   
                  bat 'kubectl apply -f deployment.yaml'
                        }
            }
            
            
        }
        }
        