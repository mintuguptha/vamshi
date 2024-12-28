pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                githubNotify context: 'Build', status: 'PENDING'
          
                script {
                    try {
                        echo 'Building...'
                        sleep 5
                        githubNotify context: 'Build', status: 'SUCCESS', description: 'Build completed successfully'
                    } catch (Exception e) {
                        githubNotify context: 'Build', status: 'FAILURE', description: 'Build failed'
                        throw e
                    }
                }
            }
        }

        stage('Test') {
            steps {
                githubNotify context: 'Test', status: 'PENDING'
                script {
                    try {
              
