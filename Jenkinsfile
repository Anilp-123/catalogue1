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
                ls -ltr
                sh 'sonar-scanner'
            }
        }
        stage('Deploying') {
            steps {
                echo "Deploying..."
            }
        }
    }
}
