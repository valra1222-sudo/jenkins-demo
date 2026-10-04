pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'git@github.com:valra1222-sudo/jenkins-demo.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }

    post {
        success {
            mail to: 'valra12.22@kmu.edu.ua',
                 subject: "SUCCESS: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                 body: "Build succeeded.\nJob: ${env.JOB_NAME}\nBuild: #${env.BUILD_NUMBER}\nDetails: ${env.BUILD_URL}"
        }
        failure {
            mail to: 'valra12.22@kmu.edu.ua',
                 subject: "FAILURE: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                 body: "Build failed.\nJob: ${env.JOB_NAME}\nBuild: #${env.BUILD_NUMBER}\nDetails: ${env.BUILD_URL}"
        }
    }
}
