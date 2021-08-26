// Define variables (based on parameters set in a Jenkins job)
// and convert them to lowercase
def jobName = env.JOB_BASE_NAME

// Conditionally define a variable 'impact'
if (jobName == 'mnr') {
  impact = "high"
} else if (env == 'dev') {
  impact = "low"
} else if (env == 'stg') {
  impact = "medium"
} else {
  impact = "unknown"
}
pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
               echo "The impact is ${impact}" 

            }
        }
    }
}
