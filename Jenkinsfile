pipeline {
    agent {
       node {
        label 'maven'
       }
    }
    stages {
        stage ( "build") {
            steps {
                sh 'mvn clean deploy'
            }
                 
        }

       stage('SonarQube analysis') {
        environment {
           scannerHome = tool 'max-SonarQube-scanner'
        }
        steps{
        withSonarQubeEnv('max-SonarQube-server') { // If you have configured more than one global server connection, you can specify its name
      sh "${scannerHome}/bin/sonar-scanner"
    }
     
  }
  
}
   

