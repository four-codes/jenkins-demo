pipeline {
    agent any
    stages {
        stage('Example') {
            def output = sh returnStdout: true, script: 'git rev-parse --short HEAD'

            steps {

              sh  echo ${output}

            }
        }
    }
}
