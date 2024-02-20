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
                sh("./mvnw clean")
            }
        }
        stage("Test") {
            steps {
                script {
                    def data = [
                        "Firstname": "Yunandar",
                        "Lastname": "Palilati"    
                    ]
                    writeJSON(file: "data.json", json: data)
                }
            }
        }
        stage("Global env") {

            enviroment {
                AUTHOR= "Yunandar Putra Palilati"    
            }
            
            steps {
                echo "Start Job: ${env.JOB_NAME}"
                echo "Start Build: ${env.BUILD_NUMBER}"
                echo "Branch Name: ${env.BRANCH_NAME}"
                echo "This pipeline is created by ${AUTHOR}"
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
