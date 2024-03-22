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
        stage('npm build') {
            steps {
                sh 'ls -ltr'
                sh 'sh 'zip -r Catalogu1.zip ./* -x "Jenkinsfile" "sonar-project.properties" ".git"'
            }
        }
        stage('Deploying') {
            steps {
                echo "Deploying..."
            }
        }
    }
}
