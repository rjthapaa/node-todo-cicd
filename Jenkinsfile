pipeline {
    agent { label "jenkins agent" }
    stages{
        stage("Clone Code"){
            steps{
                git url: "https://github.com/rjthapaa/node-todo-cicd.git", branch: "dev"
            }
        }
        stage("Build and Test"){
            steps{
                sh "docker build . -t rjthapaa/nodeimage"
            }
        }
        stage("Deploy"){
            steps{
                sh "docker-compose down && docker-compose up -d"
            }
        }
    }
}
