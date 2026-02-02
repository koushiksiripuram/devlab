CODE_CHANGES=getGitChanges()
pipeline{
  agent any 
  stages{
    stage("build"){
      when{
        expression{
          BRANCH_NAME == 'master' && CODE_CHANGES == true
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
