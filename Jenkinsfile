node('node-1')
{
    properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])
    def mavenHome = tool name: "maven3.6.2"
    
    stage('Checkout')
    {
        git branch: 'development', credentialsId: 'cacb6007-d2d3-4526-9209-00ac86b0de2a', url: 'https://github.com/NaveenTechnologiesDevOps/maven-web-application.git'
    }
    stage('Build')
    {
        sh "${mavenHome}/bin/mvn clean package"
    }
    /*
    stage('SonarQubeReportExecution')
    {
        sh "${mavenHome}/bin/mvn sonar:sonar"
    }
    stage('UploadArtifactsintoNexus')
    {
        sh "${mavenHome}/bin/mvn clean deploy"
    }
    stage('DeployToTomcat')
    {
        sshagent(['8cb67a29-bc77-44d8-90cd-8b29acbe9859']) 
        {
            sh "scp -o StrictHostKeyChecking=no target/*.war ec2-user@13.232.149.230:/opt/apache-tomcat-9.0.43/webapps/"
        }
    }
    stage('EmailNaotification')
    {
        mail bcc: 'naveenleo91@gmail.com', body: '''Build Status

        With Regards,
        Naveen''', cc: 'naveenleo91@gmail.com', from: '', replyTo: '', subject: 'Build Status', to: 'naveenleo91@gmail.com'
    } */
}
