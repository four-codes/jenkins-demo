pipeline {
    agent any
       environment {
            git_commit_id = sh(script: 'git rev-parse --short HEAD', returnStdout: true)
        }
    stages {
        stage('Example') {

            steps {

              sh '''
                echo ${git_commit_id}
              '''

            }
        }
    }
}
