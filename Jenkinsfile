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
                        echo "${scannerHome}/bin/sonar-scanner"
                        sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey='example-php' -Dsonar.projectVersion='1.0.0' -Dsonar.login=${SONARQUBE_TOKEN} -Dsonar.host.url='http://172.18.0.4:9000/' -Dsonar.exclusions='.git/**, ./*.md, ./Jenkinsfile' -Dsonar.sources='./' -Dsonar.modules='phpmodule' -Dphpmodule.sonar.sources='./', -Dphpmodule.sonar.language='php'"
                    }
                }
            }
        }
    }
}
