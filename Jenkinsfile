pipeline {
    agent any
       environment {
           GIT_COMMIT_ID = sh(script: 'git rev-parse --short HEAD', returnStdout: true)
           IMAGE_NAME = "api-${GIT_COMMIT_ID}"
           ECR_REPO="jjino/svc"
        }
    stages {
        stage('Example') {
            steps {
              sh '''
                export imageNameandversion=$ECR_REPO:$IMAGE_NAME
                sed -i "s|containerImageName|$imageNameandversion|" api-server.yml
                cat api-server.yml
              '''

            }
        }
    }
}
