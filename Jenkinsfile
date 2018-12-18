node{
   stage('SCM Checkout'){
     git 'https://github.com/GandhiBashyam/my-app'
   }
   stage('Compile-Package'){
      // Get maven home path
      def mvnHome =  tool name: 'maven-3', type: 'maven'   
      sh "${mvnHome}/bin/mvn package"
   }
   stage('SonarQube analysis') {
    withSonarQubeEnv('sonar-6') {
      // requires SonarQube Scanner for Maven 3.2+
      //sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.2:sonar'
       def mvnHome =  tool name: 'maven-3', type: 'maven'
       sh "${mvnHome}/bin/mvn sonar:sonar"
    }
  }
   //stage('Email Notification'){
    //  mail bcc: '', body: '''Hi Welcome to jenkins email alerts
    //  Thanks
     // Hari''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'hari.kammana@gmail.com'
   //}
   //stage('Slack Notification'){
       //slackSend baseUrl: 'https://hooks.slack.com/services/',
       //channel: '#jenkins-pipeline-demo',
       //color: 'good', 
      // message: 'Welcome to Jenkins, Slack!', 
       //teamDomain: 'javahomecloud',
       //tokenCredentialId: 'slack-demo'
   //}
}


