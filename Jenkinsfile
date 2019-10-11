node {
    def app

    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }
    
    stage('NPM INSTALL'){
        sh 'npm install'
    }
    
    stage('Docker Build'){
    sh ' docker build -t vybhavkadam/node-1 .'
    }
    
    stage('Push Docker Image'){
     withCredentials([string(credentialsId: 'docker-pwd', variable: 'dockerHubPwd')]) {
        sh "docker login -u vybhavkadam -p ${dockerHubPwd}"
     }
     sh 'docker push vybhavkadam/node-1'
   }

}

