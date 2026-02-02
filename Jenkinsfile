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

    stage("build") {
      steps {
        echo "Build started for version ${params.VERSION}"
      }
    }

    stage("test") {
      when {
        expression { params.executeTests }
      }
      steps {
        echo "Running tests..."
      }
    }

    stage("deploy") {
      steps {
        echo "Deploying version ${params.VERSION}"

        sh '''
          echo "Using secured credentials internally"
          # Example real command (do NOT echo credentials):
          # scp app.jar ${SERVER_CREDENTIALS_USR}@server:/opt/apps/
        '''
      }
    }
  }
}
