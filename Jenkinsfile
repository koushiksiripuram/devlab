def gv
pipeline {
  agent any

  parameters {
    choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: 'Select version to deploy')
    booleanParam(name: 'executeTests', defaultValue: true, description: 'Run test stage?')
  }

  environment {
    SERVER_CREDENTIALS = credentials('cloud-cred')
  }

  stages {
    stage("init") {
            steps {
                script {
                   gv = load "script.groovy" 
                }
            }
        }

    stage("build") {
      steps {
        script{
          gv.buildApp()
        }
      }
    }

    stage("test") {
      when {
        expression { params.executeTests }
      }
      steps {
        script{
          gv.testApp()
        }
      }
    }

    stage("deploy") {
      steps {
        script{
          gv.testApp()
        }

        sh '''
          echo "Using secured credentials internally"
          # Example real command (do NOT echo credentials):
          # scp app.jar ${SERVER_CREDENTIALS_USR}@server:/opt/apps/
        '''
      }
    }
  }
}
