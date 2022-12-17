node('nodes') {
  def mavenHome = tool name: "maven3.8.6"    
  stage('CheckOutCode')
  {
   git branch: 'developer', credentialsId: '0b207467-bb99-4e7e-88bf-a49798a2a343', url: 'https://github.com/gove007/maven-web-application.git' 
  }
  
  stage('Build')
  {
  sh "${mavenHome}/bin/mvn clean package"
  }
  /*
  stage('SonarQubeReport')
  {
  sh "${mavenHome}/bin/mvn clean sonar:sonar"
  }
  
  stage('UploadArtifactIntoNexus')
  {
  sh "${mavenHome}/bin/mvn clean deploy"
  }
  
  stage('DeployAppToTomcatServer')
  {
  sshagent(['b59bbebf-cff3-4ef4-b12c-e8c08bc31b57']) {
  sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.239.235.252:/opt/tomcat9/webapps/"
  }      
  }
  
  stage('SendEmailNotification')
  {
   emailext body: '''Build is Over...!!
   */

    Regards.
   Govardhan''', subject: 'Build over!!', to: 'tgvrdhn@gmail.com'      
  }
  
}
