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
	  sh 'docker system prune -a --volumes -f'
	}
    }
    stage ('start container and build') {
	steps {
	  sh 'docker compose up'
	  sh 'docker compose ps'
	}
    }
    stage('Run test') {
	steps {
	  sh 'curl http://localhost:9000/create_db.php'
	  sh 'curl http://localhost:9000/create_table.php'
	  sh 'curl http://localhost:9000/getting_data.php'
	  sh 'curl http://localhost:9000/insert_data.php'
	  sh 'curl http://localhost:9000/remove_data.php'
	  sh 'curl http://localhost:9000/remove_db.php'
	}
    }
  }
  post {
    always {
	sh 'docker compose down'
    }
  }
}
