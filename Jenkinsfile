node{
  def app

    stage('Clone') {
        checkout scm
    }

    stage('Build') {

      sh 'docker-compose up -d'

    }
}
