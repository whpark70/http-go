pipeline {
    agent  any
    stages {
        stage('Checkout from git') {
            checkout scm
        }
        stage('Buid image') {
            app = docker.build("whpark70/http-go")
        }
        stage('Push image') {
            docker.withRegistry("https://registry.hub.docker.com","docker-hub") {
                app.push("latest")
            }
        }
    }
}