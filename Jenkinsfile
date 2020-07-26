node{
  stage ('scm checkout') {
      git ('https://github.com/suhvas/jenkins-mvn-docker.git')
  }

  stage ('docker image build') {
     sh 'mvn clean install dockerfile:build '
  }

  stage ('Push Docker image to DockerHub') {
    withCredentials([string(credentialsId: 'dockerhubaccount', variable: 'dockerhubaccount')]) 
    {
     // sh "docker login -u suhvas -p ${dockerhubaccount}"
      sh "docker login -u suhvas -p Vastre@123"
    }
    sh 'docker push suhvas/suhas-pridevops:0.1.0'
  }
}
