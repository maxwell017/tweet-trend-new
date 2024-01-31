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
        }
}
