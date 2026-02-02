
pipeline{
  agent any 
  stages{
    stage("build"){
      when{
        expression{
              expression { env.GIT_BRANCH == 'origin/master' || env.GIT_BRANCH == 'master' }
        }
      }
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
      }
    }
  }
}
