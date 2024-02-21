@Library("jenkins-shared-library@main") _ // Library Name

import yunandar.jenkins.Output;

pipeline {
    agent any
    stages {
        stage("Global Variable") {
            steps {
                script {
                    echo(author.name())
                    echo(author.channel())
                }
            }
        }
        stage("Hello Groovy") {
            steps {
                script {
                    Output.hello(this, "Groovy")   // function to call 
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