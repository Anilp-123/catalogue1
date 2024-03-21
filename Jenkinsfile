pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Unit test') {
            steps {
                echo "Unit Testing is done here"
            }
        }
        stage('Deploying') {
            steps {
                echo "Deploying..."
            }
        }
    }
    post {
        always {
            echo "I will always run......"
        }
        success {
            echo "I will Only run if the job is success......"
        }
    }
}
