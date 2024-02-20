pipeline {
    agent none
    
    enviroment {
        AUTHOR= "Yunandar Putra Palilati"    
    }

    stages {
        stage("Global env") {          
            steps {
                echo "Start Job: ${env.JOB_NAME}"
                echo "Start Build: ${env.BUILD_NUMBER}"
                echo "Branch Name: ${env.BRANCH_NAME}"
                echo "This pipeline is created by ${AUTHOR}"
            }
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
