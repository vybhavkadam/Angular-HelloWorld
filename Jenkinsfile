pipeline {
   agent any
      environment {
         PATH='/var/lib/jenkins/workspace/angular'
      }

 
    stages { 
        stage('Build Docker Image') { 
            steps { 
                sh 'docker build -t vybhavkadam/node-web-app .' 
            } 
        } 
    }
}
