pipeline {
    agent any 
    stages {
        stage('cloning') { 
            steps {
                git branch: 'main', credentialsId: 'aditya', url: 'https://github.com/aditya0660/website-jenkins.git' 
            }
        }
        stage('deploying') { 
            steps {
                sh 'ls'
                sh 'pwd'
                sh 'cp $(pwd) . scp -r root@172.21.242.50:/home'
                
            }
        }        
    }
}
