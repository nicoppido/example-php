pipeline {
    agent { 
        label 'master' 
    }
    environment {
        scannerHome = tool 'SonarQubeScanner'
        mvnHome = tool 'Maven'
    }
    stages {
            stage('Code Analysis') {
             steps {
                    withSonarQubeEnv('SonarQube') {
                        sh "${scannerHome} -Dsonar.host.url=http://172.18.0.4:9000/ -Dsonar.projectName="PHP Example" -Dsonar.projectVersion=1.0 -Dsonar.sourceEncoding=UTF-8 -Dsonar.projectKey=php-example -Dsonar.sources=. -Dsonar.projectBaseDir=/var/jenkins_home/workspace/"
                    }
             }
        }
    }

}
