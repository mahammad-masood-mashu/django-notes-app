@Library('shared')_
pipeline{
    agent { label 'masood'}
    
    stages{
        stage("hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("Code"){
            steps{
               script{
                   clone("https://github.com/mahammad-masood-mashu/django-notes-app.git","main")
               }
            }
        }
        stage("Code Build"){
            steps{
                script{
                docker_build("notes-app","latest","macchuu1")
                }
            }
        }
        stage("Push to DockerHub"){
            steps{
                script{
                    docker_push("notes-app","latest", "macchuu1")
                }
        }
        }
        stage("Deploy"){
            steps{
                echo "Deploying the project"
                sh "docker compose up -d"
                echo "deployed"
                
            }
        }
        
    }
}
