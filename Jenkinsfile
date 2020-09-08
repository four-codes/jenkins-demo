pipeline {
    agent any
    stages {
        stage('Docker Image Build') { 
            steps {
                sh 'docker --version'
            }
        }
        stage('Docker image build') { 
            steps {
                sh 'docker build  -t jjino/bcd-server .'
            }
        }
        stage('push registry') { 
            steps {
                sh '''
                echo "jino@1234" | docker login -u "jjino" --password-stdin
                docker push jjino/bcd-server:latest
                docker logout
                '''
            }
        }
    }
    post {
        always {
            echo 'One way or another, I have finished!'
            deleteDir() 
        }
        success {
            echo 'I succeeeded!'
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
        }
        changed {
            echo 'Things were different before...'
        }
    }
}
