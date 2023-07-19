@Library('my-shared-library') _
pipeline {
    agent { label "dev-server" }
    stages{
        stage("Build and Test"){
            steps{
              call()
            }
        }
        stage("Clone Code"){
            steps{
                git url: "https://github.com/LondheShubham153/node-todo-cicd.git", branch: "master"
            }
        }
        // stage("Build and Test"){
        //     steps{
        //         sh "docker build . -t node-app-test-new"
        //     }
        // }
}
}
