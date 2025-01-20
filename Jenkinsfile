pipeline {
    agent {
        docker {
            image "maven:3.8.7-openjdk-18-slim"
        }
    }
    stages {
        stage('Hello') {
            steps {
                sh '''
                    mvn -version
                    mvn clean install
                '''
            }
        }
    }
    /*
    post {
        always {
            cleanWs()
        }
    }
    */
}
