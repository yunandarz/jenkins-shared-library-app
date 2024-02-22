@Library("jenkins-shared-library@main") _ // Library Name

import yunandar.jenkins.Output;

pipeline {
    agent any
    stages {
        stage("Hello person") {
            steps {
                script {
                    hello.person([  // call map parameter
                        firstName: "Yunandar",
                        lastName: "Palilati"
                    ])
                }
            }
        }
        stage("Maven compile") {
            steps {
                script {
                    maven(["clean", "compile", "test"])  // call function parameter
                }
            }
        }
        stage("Global Variable") {
            steps {
                script {
                    echo(author()) // call default function
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