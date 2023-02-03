pipeline {
  agent any

  stages {
    stage('clone') {
	steps {
            checkout scm
	}
    }
    stage ("prune docker data") {
	steps {
	  sh 'docker system prune -a --volumes -f
	}
    }
    stage ('start container and build') {
	steps {
	  sh 'docker compose up -d --wait'
	  sh 'docker compose ps'
	}
    }
    stage('Run test') {
	steps {
	  sh 'curl http://localhost:9000'
	}
    }
  }
  post {
    always {
	sh 'docker compose down'
    }
  }
}
