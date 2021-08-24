pipeline {
    agent any
       environment {
           
            git_commit_id = sh(script: 'git rev-parse --short HEAD', returnStdout: true)
           IMAGE_NAME = "api-${git_commit_id}"
        }
    stages {
        stage('Example') {

            steps {

              sh '''
                echo ${IMAGE_NAME}
              '''

            }
        }
    }
}
