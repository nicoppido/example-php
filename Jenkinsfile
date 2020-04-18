pipeline {
    agent { 
        label 'master' 
    }
    environment {
        scannerHome = tool 'SonarQubeScanner'
    }
    stages {
        stage('Code Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    withCredentials(bindings: [string(credentialsId: 'SonarQubeToken', variable: 'SONARQUBE_TOKEN')]) {
                        echo "${scannerHome}"
                        echo "${SONARQUBE_TOKEN}"
                    }
                }
            }
        }
    }
}
