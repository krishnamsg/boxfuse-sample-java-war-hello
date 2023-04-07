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
             deploy adapters: [tomcat9(credentialsId: 'bhupesh1', path: '', url: 'http://13.234.78.182:8080')], contextPath: '100apps', war: '**/*.war'
          }
      }
  }
}
