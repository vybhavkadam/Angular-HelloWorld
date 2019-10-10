node {
    def app

    stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

        checkout scm
    }
     stage('Build image') {
        /* This builds the actual image */
    
        //app = docker.build("vybhavkadam/nodeapp")
         docker build -t <your username>/node-web-app
     }


}
