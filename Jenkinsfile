pipeline {
    agent { 
        label 'master' 
    }
    stages {
        stage('Print env') {
            steps {
                sh 'printenv'
            }
        }
        stage('Code Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    echo "${SONAR_RUNNER_HOME}"
                }
            }
        }
    }
}
