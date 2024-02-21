@Library("jenkins-shared-library@main") _ // Library Name

import yunandar.jenkins.Output;

pipeline {
    agent any
    stages {
        stage("Hello Groovy") {
            steps {
                script {
                    Output.hello("Groovy")   // function to call hello world
                }
            }
        }
        stage("Hello World") {
            steps {
                script {
                    hello.world()   // function to call hello world
                }
            }
        }
    }
}