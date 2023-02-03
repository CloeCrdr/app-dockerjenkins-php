pipeline {
  agent any

  stages {
    stage('clone') {
	steps {
            checkout scm
	}
    }
    stage ('start container and build') {
	steps {
	  sh 'docker-compose up'
	  sh 'docker-compose ps'
	}
    }
  }
  post {
    always {
	sh 'docker compose down'
    }
  }
}
