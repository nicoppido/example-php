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
                        echo "${scannerHome}"
                        def projectKey = "example-php"
                        def projectVersion = "1.0.0"
                        def login = "${SONARQUBE_TOKEN}"
                        def hostUrl = "http://172.18.0.4:9000/"
                        def exclusion = ".git/**, ./*.md, ./Jenkinsfile"
                        def sources = "."
                    
                        def command = "${scannerHome}" +
                            " -Dsonar.projectKey=" + projectKey +
                            " -Dsonar.projectVersion=" + projectVersion +
                            " -Dsonar.login=" + login +
                            " -Dsonar.host.url=" + hostUrl +
                            " -Dsonar.exclusions=" + exclusion +
                            " -Dsonar.sources=" + sources
                        echo command
                    }
                }
            }
        }
    }
}
