

node('master') 
{
      stage('ContinousDownload')
     {
          git 'https://github.com/prempurohit/maven-july.git'
      }
   
       stage('ContinousBuild')
      {
         sh label: '', script: 'mvn package' 
       }
   
       stage('ContinusDeployment')
      {
         sh label: '', script: 'scp       /home/ubuntu/.jenkins/workspace/PipeLine/webapp/target/webapp.war ubuntu@172.31.37.229:/var/lib/tomcat8/webapps/TestEnv.war'
      }
   
      stage('ContinousTsting')
     {
        git 'https://github.com/selenium-saikrishna/Functionaltesting.git'
        sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/PipeLine/testing.jar'
     }
   
     stage('ContinusDeplivery')
     {
        sh label: '', script: 'scp   /home/ubuntu/.jenkins/workspace/PipeLine/webapp/target/webapp.war ubuntu@172.31.83.53:/var/lib/tomcat8/webapps/ProdEnv.war'
     }
}



