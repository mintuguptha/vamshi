pipeline{
  agent any
  stages{
    stage('echo'){ 
      steps{
         script{echo 'hello world'}
      }
    }
    stage('notify github'){
      steps{
        script{
          if(currentBuild.result == 'SUCCESS'){
            githubNotify status: 'success', context: GITHUB_STATUS
          }else{
            githubNotify status: 'failure', context: GITHUB_STATUS
          }
        }
      }
    }
  }
}
