@Library('my-shared-library') _
pipeline {
    agent any 
    stages{
        stage("Build and Test"){
            steps{
                script{
              hello.call1()
            }
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
