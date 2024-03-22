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
        stage('npm build') {
            steps {
                sh 'ls -ltr'
                sh 'zip -r Catalogue1.zip ./* -x "sonar-project.properties" ".git/*" "Catalogue1.zip"'
            }
        }
        stage('Artifact Upload Nexus') {
            steps {
                nexusArtifactUploader(
                    nexusVersion: 'nexus3',
                    protocol: 'http',
                    nexusUrl: '18.235.2.143:8081/',
                    groupId: 'com.roboshop',
                    version: '1.0.0',
                    repository: 'Catalogue1',
                    credentialsId: 'nexus-auth', // Use the correct credentials ID here
                    artifacts: [
                        [artifactId: 'Catalogue1',
                        classifier: '',
                        file: 'Catalogue1.zip',
                        type: 'zip']
                    ]
                )
            }
        }
        stage('Deploying') {
            steps {
                echo "Deploying..."
                // Add deployment steps here if needed
            }
        }
    }
    post {
        always {
            echo 'One way or another, I have finished'
            deleteDir() // Delete workspace after pipeline execution
        }
    }
}
