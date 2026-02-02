
pipeline{
  agent any 
  environment{
    SERVER_CREDENTIALS = credentials('cloud-cred')
  }
  stages{
    stage("build"){
      
      steps{
        echo "build started"
      }
    }
    stage("test"){
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
          sh "hello ${USER} "
        }
      }
    }
  }
}
