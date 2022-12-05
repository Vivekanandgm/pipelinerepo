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
        git clone https://github.com/Vivekanandgm/pipelinerepo.git
        if [ $? -eq 0 ] ; then
          git add *
          git commit -m "Adding iles from gir repo"
          echo "Cloned succesfully" 
        else
          git pull https://github.com/Vivekanandgm/pipelinerepo.git
          git add *
          git commit -m "Adding files from git repo"
          echo "pulled succesfully" 
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
