pipeline {
  agent any
    parameters {
  choice choices: ['make', 'mvn clean package'], description: 'choose your build', name: 'BUILD'
}
  stages {
    stage ('git clone'){
      steps {
         git branch: 'master', credentialsId: 'dba4200a-8fce-417d-a08d-78ce042c98af', url: 'https://github.com/Vivekanandgm/pipelinerepo.git'
        sh '''
         echo "cloned succesfully" 
        '''
      }
    }
      stage ('parameter') {
        steps {
          sh '''
          ${BUILD}
          '''
        }
      } 
  }
}
