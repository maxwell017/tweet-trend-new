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

        stage("test"){
            steps{
                echo "----------- unit test started ----------"
                sh 'mvn surefire-report:report'
                 echo "----------- unit test Complted ----------"
            }
        } 

        stage('SonarQube analysis') {
    environment {
      scannerHome = tool 'maxwell01-sonarQube-server'
    }
    steps{
    withSonarQubeEnv('maxwell01-sonarQube-scanner') { // If you have configured more than one global server connection, you can specify its name
      sh "${scannerHome}/bin/sonar-scanner"
    }
    }
  }  
        }
}
