pipeline {
    agent any 
    stages {
        stage('cloning') { 
            steps {
                git branch: 'main', credentialsId: '1', url: 'https://github.com/aditya10mm/sample-website-for-practise' 
            }
        }
        stage('deploying') { 
            steps {
                sh 'ls'
                sh 'pwd'
                sh 'scp -r ./ root@13.233.8.118:/home'
                
                
            }
        }        
    }
}
