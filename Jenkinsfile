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
                sh("./mvnw clean compile tes-compile")
            }
        }
        stage("Test") {
            steps {
                echo "testing app"
                sh("./mvnw test")
                echo("Finish Build")
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
