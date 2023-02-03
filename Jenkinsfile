pipeline {
    stages {
	stage('Clone') {
		steps {
			echo 'Cloning your repository...'
			checkout scm
		}
	}
	stage('Build') {
		steps {
			echo 'Server is beein built'
			sh 'docker-compose up -d'
		}
	}
	stage('Launch') {
		steps {
			echo 'Test launching the server'
			sh 'curl localhost:8080'
		}
	}
    }
}
