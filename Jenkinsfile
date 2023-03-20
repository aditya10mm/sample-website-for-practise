pipeline {
    agent any
    environment{
        prod_ip = "13.233.8.118"
        prod_user = "root"
        dev_ip = ""
        dev_user = ""
    } 
    parameters {
        choice choices: ['dev', 'production'], 
            description: 'chose the environment to deploy', 
             name: 'appenv'
     }
    stages {
        stage('deploy to production') { 
            when {
                expression{
                    params.appenv == "production"
                } 
            }
            steps {
                git branch: 'main', credentialsId: '1', url: 'https://github.com/aditya10mm/sample-website-for-practise' 
            }
            steps {
                echo "Deploying to ${prod_ip} using user${prod_user}"
                sh 'ls'
                sh 'pwd'
                sh 'scp -r $(pwd)/* $(prod_user}@${prod_ip}:/home'
            }
        }
        stage('deploy to dev') { 
            when {
                expression{
                    params.appenv == "dev"
                } 
        stage('deploying to Dev') { 
            steps {
                git branch: 'dev', credentialsId: '1', url: 'https://github.com/aditya10mm/sample-website-for-practise.git' 
            }
            steps {
                echo "Deploying to dev with ${dev_ip} user {dev_user}"
                sh 'ls'
                sh 'pwd'
                sh 'scp -r $(pwd)/* root@13.233.8.118:/home'
            }
        }        

    }
}