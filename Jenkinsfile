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
            githubNotify status: 'success', context: 'ci_success'
          }else{
            githubNotify status: 'failure', context: 'ci_failure'
          }
        }
      }
    }
  }
}
