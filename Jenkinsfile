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
                sh 'zip -r Catalogue1.zip ./* -x "sonar-project.properties" ".git/*" "Catalogue1.zip"'
            }
        }
        stage('articat upload nexus'){
            steps {
                nexusArtifactUploader(
                nexusVersion: 'nexus3',
                protocol: 'http',
                nexusUrl: '18.235.2.143:8081/',
                groupId: 'com.roboshop',
                version: '1.0.0',
                repository: 'Catalogue1',
                credentialsId: 'nexus-auth',
                artifacts: [
                    [artifactId: 'Catalogue1',
                    classifier: '',
                    file: 'Catalogue1.zip',
                    type: '.zip']
                ]
     )
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
            echo 'One way or another, I have finished'
            deleteDir() 
        }
    }
}
