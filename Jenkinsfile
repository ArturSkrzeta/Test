node {
  def app
  
    stage('Clone repository') {
      checkout scm
    }

    stage('Build image') {
      app = docker.build("arturskrrr/webpage")
    }

    stage('Push image') {
      docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
        app.push()
    }
  }
}
