pipeline {
    agent { docker { image 'golang' } }
    stages {
        stage('build') {
            steps {
                timeout(time: 3, unit: 'MINUTES') {
                    retry(5) {
                        bat 'set'
                    }
                }
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Fail!"; exit 1'
            }
    }
    post {
        always {
            echo 'This will always run MJ1'
        }
        success {
            echo 'This will run only if successful MJ2'
        }
        failure {
            echo 'This will run only if failed MJ3'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable MJ4'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed MJ5'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
