pipeline {
    agent any
       environment {
           GIT_COMMIT_ID = sh(script: 'git rev-parse --short HEAD', returnStdout: true)
           IMAGE_NAME = "api-${GIT_COMMIT_ID}"
        }
    stages {
        stage('Example') {
            steps {
              sh '''
                export imageNameandversion=$IMAGE_NAME
                sed -i "s|containerImageName|$imageNameandversion|" api-server.yml
                cat api-server.yml
              '''

            }
        }
    }
}
