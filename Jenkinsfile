pipeline {
    agent any  
    stages {
	stage ('build') {steps {echo 'inside build stage'}}
	stage ('test') {steps {echo 'inside test stage'}}
	stage ('deploy') {steps {echo 'inside deploy stage'}}
	    stage ('docker container run') {
		    steps {
			    sh 'docker run hello-world'
		    }}
		    
          }
}
    
