node {
    def app

    stage('Clone repository') {
       checkout scm 
    }

    stage('Build image') {
        app = docker.build('barameno/example-app')
    }

    stage('Push image') {
        docker.widthRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
            app.push('latest')
        }
    }
}
