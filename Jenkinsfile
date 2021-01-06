pipeline {
  agent any
  options {
    timeout(time: 2, unit: 'HOURS')
    timestamps()
  }
  
  stages {
   stage('SonarQube') {
      steps {
        sh "pwd"
        sh "ls -ltr"
        script {
          def scannerHome = tool 'SonarRunner'
          withSonarQubeEnv('SonarRunner') { 
            //sh "${scannerHome}/bin/sonar-scanner"
            sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=${env.JOB_BASE_NAME}"
          }
        }
      }
    }
  }
}
