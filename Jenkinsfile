node{
  def app

    stage('Clone') {
        checkout scm
    }

    stage('Build') {

      sh 'docker-compose up -d'

    }
    stage('Test') {

      sh 'curl localhost:9000'

    }	
}
