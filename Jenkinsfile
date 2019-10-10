node {
    def app

    
        
    
    stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

        checkout scm
    }
    
    stage('NPM INSTALL'){
        sh 'npm install'
    }
    
   
     stage('Build image') {
        /* This builds the actual image */
    
        //app = docker.build("vybhavkadam/nodeapp")
         
         sh 'docker build -t vybhavkadam/node-webapp:2.0.0 .'
     }


}
