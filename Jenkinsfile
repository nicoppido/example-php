pipeline {
    agent { 
        label 'master' 
    }
    stages {
        stage('Code Analysis') {
            steps {
                echo '${SONAR_RUNNER_HOME}'
            }
        }
    }
}
