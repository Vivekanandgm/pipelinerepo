pipeline {
  agent none
    parameters {
  choice choices: ['make', 'mvn clean package'], description: 'choose your build', name: 'BUILD'
}
  stages {
    stage ('git clone'){
      agent { label 'slave001'}
      steps {
         git branch: 'master', credentialsId: 'dba4200a-8fce-417d-a08d-78ce042c98af', url: 'https://github.com/Vivekanandgm/pipelinerepo.git'
        sh '''
         echo "cloned succesfully" 
        '''
      }
    }
      stage ('parameter') {
        agent { label 'slave001'}
        steps {
          sh '''
          ${BUILD}
          '''
        }
      } 
  }
}
