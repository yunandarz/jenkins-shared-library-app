pipeline {
  agent {
    node {
      label "linux && java11"
    }
  }

  environment {
    AUTHOR = "Yunandar Putra Palilati"
  }

  stages {
    stage("Preparation") {
      steps {
        echo "Prepare Java"
        // You can add additional steps to prepare Java here, such as downloading packages
        sh "./mvnw -version" // Check Maven version
      }
    }

    // Build stage
    stage("Build") {
      steps {
        echo "Build process begin"
        sh "./mvnw clean verify" // Run mvnw clean verify 
      }
    }

    // Test stage
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

    // Global environment stage
    stage("Global env") {
      steps {
        echo "Start Job: ${env.JOB_NAME}"
        echo "Start Build: ${env.BUILD_NUMBER}"
        echo "Branch Name: ${env.BRANCH_NAME}"
        echo "This task is created by ${AUTHOR}"
      }
    }

    // Deploy stage with manual approval
    stage("Deploy") {
      input {
        message "Can we deploy?"
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
        // Add actual deployment steps based on your target environment
      }
    }

    // release stage
    stage("Release") {
      steps {
        withCredentials([usernamePassword(
            credentialsId: "Yunandar",
            usernameVariable: "USER",
            passwordVariable: "PASSWORD"
          )]){
          sh ('echo "Relese with u $USER -p $PASSWORD"')
      }
    }
    
  }

  post {
    always {
      echo "Always learning"
    }
    success {
      echo "Big success starts with small victories"
    }
    failure {
      echo "Don't give up when you fail"
    }
    cleanup {
      echo "Always tidy your bedroom when you wake up"
    }
  }
}

