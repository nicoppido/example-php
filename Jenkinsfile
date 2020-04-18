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
                echo env.WORKSPACE;
            }
        }
    }
}
