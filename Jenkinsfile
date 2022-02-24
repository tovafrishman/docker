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
        stage('push'){
            steps {
                withDockerRegistry([url: "", credentialsId: "dockerbuildbot-index.docker.io"]) {
                    sh("docker push docker/getting-started")
                }
            }
        }
    }
}
