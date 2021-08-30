def jobName = env.JOB_BASE_NAME

if (jobName == 'staging-deployment') {
  impact = "staging"
} else if (env == 'production-deployment') {
  impact = "production"
} else if (env == 'stg') {
  impact = "medium"
} else {
  impact = "unknown"
}

pipeline {
    agent any
    environment {
      namespace="${impact}"
    }
    stages {
        stage('Example') {
            steps {
              script {
                  def branchName = "${env.BRANCH_NAME}"
                  echo "${branchName}"
                }
            }
        }
    }
}
