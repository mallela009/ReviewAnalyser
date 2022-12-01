pipeline {	 
    agent any	 
   	 stages {     	 
   	 stage("Compile") {          	 
   			 steps {               	 
   				 echo "mvn compile"          	 
   			 }     	 
   		 }     	 
   	 stage("Unit test") {          	 
   		 steps {               	 
   				 echo  "mvn test"          	 
   			 }     	 
   		 }	 
   	 }

    	post {
   	 always {
   	 step([$class: 'JacocoPublisher',
   	   	execPattern: 'target/*.exec',
   	   	classPattern: 'target/classes',
   	   	sourcePattern: 'src/main/java',
   	   	exclusionPattern: 'src/test*'
   	 ])
   	 }   
    	}
}

