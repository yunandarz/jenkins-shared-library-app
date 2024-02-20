pipeline {
    agent {
      node {
        label "linux && java11"
      }
    }

    environment {
    AUTHOR = "Yunandar Putra Palilati"
    }

    //options {
    //    disableConcurrentBuilds()
    //    timeout(time: 30, unit: 'SECONDS')
    //}
    
    stages {

        stage("Preparation") {
            stages {
                stage("Prepare Java") {
                    steps {
                        echo "Prepare Java"
                    }
                }
            }
            stages {
                stage("Prepare Maven") {
                    steps {
                        echo "Prepare maven"
                    }
                }
            }
        }
        
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
            steps {
                echo "Start Job: ${env.JOB_NAME}"
                echo "Start Build: ${env.BUILD_NUMBER}"
                echo "Branch Name: ${env.BRANCH_NAME}"
                echo "This task is created by ${AUTHOR}"
            }
        }

        stage("Deploy") {
            input {
                message "can we deploy?"
                ok "Yes, of course"
                parameters {
                    choice(name: 'TARGET_ENV', choices: ['DEV', 'QA', 'PRODUCTION'], description: 'Deploy to?')
                }
            }
            agent {
                node {
                    label "linux && java11"
                }
            }
            steps {
                echo "Deploy to ${TARGET_ENV}"
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
