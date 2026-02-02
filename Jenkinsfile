
pipeline{
  agent any 
  environment{
    SERVER_CREDENTIALS = credentials('cloud-cred')
  }
  parameters {
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
  stages{
    stage("build"){
      
      steps{
        echo "build started"
      }
    }
    stage("test"){
      when{
        expression{
          params.executeTests
        }
      }
      
      steps{
        echo "build started"
      }
    }
    stage("deploy"){
      steps{
        echo "build started"
        echo "deploying with ${SERVER_CREDENTIALS}"
        withCredentials([
          usernamePassword(credentialsId:'cloud-cred',usernameVariable: USER,passwordVariable: PWD)
        ]){
          sh "echo ${USER}"
        }
      }
    }
  }
}
