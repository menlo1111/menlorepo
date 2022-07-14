

pipeline
{
    agent any
    stages
    {
       stage('ContinuousDownload_master')
       {
           steps
           {
              git 'https://github.com/selenium-saikrishna/maven.git' 
           }
       }
        stage('ContinuousBuild_master')
       {
           steps
           {
             sh 'mvn package'
           }
       }
         stage('ContinuousDeployment_master')
       {
           steps
           {
      deploy adapters: [tomcat9(credentialsId: 'da16f60f-4542-4db8-99dc-81bfb6d72719', path: '', url: 'http://172.31.83.121:8080')], contextPath: 'testapp', war: '**/*.war'
           }
   
}
