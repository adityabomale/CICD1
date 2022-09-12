pipeline {
    agent any  
/*	tools {
		maven "Maven"
	}
	*/
    stages {
	stage ('build') {steps {echo 'inside build stage'}}
	stage ('test') {steps {echo 'inside test stage'}}
	stage ('deploy') {steps {echo 'inside deploy stage'}}
	    stage ('checkout') {
		    steps {
			    git branch: 'master', url: 'https://github.com/adityabomale/CICD1.git'
		    }
	    }
	/*    stage ('maven build'){
		    steps{ 
			    sh 'mvn package'
		    }
	    }
	  */  stage ('remove existing containers'){
	    	steps{
			sh 'docker stop $(docker ps -a -q)'
			sh 'docker rm $(docker ps -a -q)'
		}
	  }
	    
	    stage ('Docker build'){
		    steps {
			   sh 'docker build -t sampleimage:latest .' 
			    sh 'docker tag sampleimage aditya/sampleimage:latest'
		    }
	    }
	    stage ('run docker'){
		    steps {
			    sh "docker run -d -p 8090:8080 aditya/sampleimage"
		    }
	    }
	  /*  stage ('run docker on remote server'){
		    steps {
			    sh 'docker -H ssh://root@43.204.214.44 run -d -p 8090:8080 aditya/sampleimage'
		    }
	    }
		*/    
          }
}
    
