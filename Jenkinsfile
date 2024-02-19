pipeline {
    agent {
      node {
        label "linux && java11"
      }
    }
    stages {
        stage("Hello World") {
            steps {
                echo "Hello World!"
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
