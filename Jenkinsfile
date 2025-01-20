pipeline {
    agent any
    stages {
        stage('Hello') {
            agent {
                docker {
                    image 'maven-build'
                    reuseNode true
                }
            }
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
            steps {
                sh '''
                    mvn package
                    mvn install
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
