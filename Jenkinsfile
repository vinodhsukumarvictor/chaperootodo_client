pipeline {
    agent any
    
    environment {
        DB_PASSWORD = credentials('DB_PASSWORD')
    }

    stages {
        stage('checkout source code') {
            steps{
                git url: "https://github.com/vinodhsukumarvictor/chaperootodo_client",branch: "master"
            }
        }
         
        stage('Build')   {
             steps {
                 sh 'docker build -t chaperoo-client:v2 .'
             }
         }
         
        stage('run containers') {
             steps {
                sh 'docker-compose up -d --build'
             }
             
         }

    }
}
