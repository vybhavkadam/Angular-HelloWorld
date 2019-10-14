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

    stage('Run Container on test2'){
     def dockerRun = 'docker run -p 8080:8080 -d --name my-app-2 vybhavkadam/node-1'
     sshagent(['test2']) {
       sh "ssh -o StrictHostKeyChecking=no ubuntu@54-227-63-170 ${dockerRun}"
     
     }
    }
    
    stage ('Email Notificcation'){
        mail bcc: '', body: '''Hi welcome to Jenkins
Thanks
''', cc: '', from: '', replyTo: '', subject: 'jenkins', to: 'vybhavkadam@live.com'
    }
    
   
}

