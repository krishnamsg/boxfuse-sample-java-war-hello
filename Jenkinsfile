pipeline 
{

  agent any
  environment 
	{
      	PATH = "/bin/mvn:$PATH"
  	}
  
stages 
{
      
	stage("Code Collect")
	{
          steps
		{
            	git branch: 'master', url: 'https://github.com/GREATCODERHYD/boxfuse-sample-java-war-hello.git'
          
        	  }
      }
      stage("building code"){
          steps
		{
              sh "mvn clean package"
          	}
      }
      
stage("deploy"){
          steps{
             deploy adapters: [tomcat9(credentialsId: 'tomcat_credentials', path: '', url: 'http://192.168.56.101:8090')], contextPath: '100apps', war: '**/*.war'
          }
      }
  }
}
