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
              sh "mn clean package"
          	}
      }
      
stage("deploy"){
          steps{
             deploy adapters: [tomcat9(credentialsId: '1010', path: '', url: 'http://65.2.127.59:8080/')], contextPath: 'test1', war: '**/*.war'
          }
      }
  }
}
