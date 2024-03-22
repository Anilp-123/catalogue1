pipeline {
    agent {
        node {
            label 'AGENT_1'
        }
    }
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        // stage('Unit test') {
        //     steps {
        //         echo "Unit Testing is done here"
        //         sh 'ls -ltr'
        //         sh 'sonar-scanner'
        //     }
        // }
        stage {
            steps{
                sh 'ls -ltr'
                sh 'npm build'
            }
        }
        stage('Deploying') {
            steps {
                echo "Deploying..."
            }
        }
    }
}
