pipeline {
    agent any
    
    environment {
        DB_PASSWORD = credentials('DB_PASSWORD')
    }

    stages {
         
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
