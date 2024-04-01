pipeline {

    agent any

    
    stages {
         stage('build') {
          steps {
              sh 'npm install'
            }
          }
        
        stage('Test') {
            steps {
               
                    sh "sudo npm-test"
                
            }
        }
        
        stage('Docker Comopse Up') {
            steps {
               
                    sh "sudo docker-compose-up"
                
            }
        }
         stage('kill') {
            steps {
               
                    sh "sudo docker-compose-down"
                
            }
        }
    }
}
