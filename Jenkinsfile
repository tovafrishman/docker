pipeline {
    options {
        timeout(time: 1, unit: 'HOURS')
    }
    agent any
    stages {
        stage('build') {
            when {
                branch 'master'
            }
             steps {
                sh "docker build -t tovafrishman/getting-started ."
             }
        }
        stage('Login') {

			steps {
				sh "echo 043399351 | docker login -u tovafrishman@gmail.com --password-stdin"
			}
		}
        stage('push'){
		steps {
                    sh("docker push docker/getting-started")
                }
            }
        }
    }
