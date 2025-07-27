pipeline{
  agent {
    label 'aws-agent'
  }
  stages{
    stage('build'){
      steps{
        script{
          sh'mvn clean package'
        }
      }
    }
  }

  post {
  success {
    slackSend channel: '#jenkins-ci', color: 'slackSend color: "#439FE0", message: "Build Started: ${env.JOB_NAME} ${env.BUILD_NUMBER}"', message: 'slackSend "started ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)"', teamDomain: 'first-workplacehq', tokenCredentialId: 'slack-bot-token'
  }
  failure {
        slackSend channel: '#jenkins-ci', color: 'slackSend color: "#439FE0", message: "Build failed: ${env.JOB_NAME} ${env.BUILD_NUMBER}"', message: 'slackSend "started ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)"', teamDomain: 'first-workplacehq', tokenCredentialId: 'slack-bot-token'

  }
}


}