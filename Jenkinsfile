pipeline {
    agent any
    stages{
        stage("Code "){
            steps{
                git url: 'https://github.com/vishwanath0303/node-todo-cicd.git' , branch: 'master'
            }
        }
        stage("Build & Test "){
            steps{
                sh "docker build . -t node-app-test-new "
            }
        }
        stage("PUSH TO REPO "){
            steps{
                withCredentials([usernamePassword(credentialsId:"dockerhub",passwordVariable:"dockerHubPass",usernameVariable:"dockerHubUser")]) {
                    sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass} "
                    sh "docker tag node-app-demo  ${env.dockerHubUser}/node-app-test-new:latest"
                    sh "docker push ${env.dockerHubUser}/node-app-test-new:latest"
                } 
            }
        }
        
        stage("Removing the conatainer"){
            steps{
                sh "docker container ls"
                sh "docker rm -f node-app "
            }
        }
        
        stage("Deploy "){
            steps{
                sh "docker run --name node-app -d -p 8000:8000  node-app-test-new "
            }
        }
    }
}
