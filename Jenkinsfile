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
        stage('Testing'){
            steps {
                sh '''
                    echo 'Testing is in progress...'
                    mvn test
                '''
            }
        }
        stage('Package & Install'){
            sh '''
                mvn package
                mvn install
            '''
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
