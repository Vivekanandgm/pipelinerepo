pipeline {
  agent any
  stages {
    stage ('git clone'){
      steps {
         git branch: 'master', credentialsId: 'dba4200a-8fce-417d-a08d-78ce042c98af', url: 'https://github.com/Vivekanandgm/pipelinerepo.git'
        sh '''
        echo "Cloned succesfully" 
        '''
      }
    }
      stage ('Build with maven'){
        steps {
          sh '''
          mvn clean package
          '''
        }
      } 
  }
}
