pipeline {
    agent {
      node {
        label "linux && java11"
      }
    }
    stages {
        stage("Build") {
            steps {
                echo "build process begin"
            }
        }
        stage("Test") {
            steps {
                echo "testing app"
            }
        }
        stage("Deploy") {
            steps {
                echo "Deploying . . ."
            }
        }
    }
    
    post {
        always {
           echo "Always learning" 
        }
        success {
            echo "Big success start with small victories"
        }
        failure {
            echo "don't give up when fail"
        }
        cleanup {
            echo "always tide your bedroom when wake up"
        }
    }
    
}
