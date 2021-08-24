pipeline {
    agent any
    stages {
        stage('Example') {
          environment {
            git_commit_id = sh(script: 'git rev-parse --short HEAD', returnStdout: true)
        }
            steps {

              sh '''
                echo $git_commit_id
              '''

            }
        }
    }
}
