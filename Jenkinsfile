pipeline 
{
	agent any
		environment {
			PATH = "/bin/:$PATH"
		}

stages
	{
		stage("Get the code from git=bijoy")
		{
			steps 
            	{
                		git branch: 'main', url:'https://github.com/Sushant293/sample.git'
            	}
        	}
         	stage("Build the code") 
        	{
            	steps 
            	{
                		sh "mvn clean package"
            	}
        	}
        	stage("Deploy the code") 
        	{
            	steps 
            	{
                		deploy adapters: [tomcat9(credentialsId: '75ee2c93-a95d-4029-b0e9-c6f7ad734cee', path: '', url: 'http://35.170.196.2:8080/')], contextPath: 'vijaypipe', war: '**/*.war'
            	}
        	}
    	}
} 
