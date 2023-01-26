node {
    def app

    stage('Clone repository') {
        checkout scm
    }

    stage('Build image') {
        app = docker.build("balachandar126/rsa_nodejs_app")
    }

    stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com', 'dockerhubcredentials') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}


