pipeline {
    agent {
      label "jenkins-jx-base"
    }
    environment {
      ORG               = 'theakshashetty'
      APP_NAME          = 'newpipeline'
      CHARTMUSEUM_CREDS = credentials('jenkins-x-chartmuseum')
    }
    stages {
      stage('Build Release') {
        when {
          branch env.BRANCH_NAME
        }
        steps {
          container('jx-base') {
            // ensure we're not on a detached head
            sh "echo newpipeline"
          }
        }
      }
    }
    post {
        always {
            cleanWs()
        }
    }
  }
