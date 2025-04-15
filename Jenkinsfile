pipeline {
  agent {
    kubernetes {
      label 'jenkins-npm'
     // defaultContainer 'jnlp'
    }
}

 stages {
 
stage('Unit-Test') {

	when { expression { params.ACTION == 'Unit-Test' } }
	
	steps { 
		container('node') {
	
				echo "Unit-Test"
	
				 sh "npm test"
	
		}
	}
}
 
stage('Maven_Build') {

	when { expression { params.ACTION == 'Build' } }

	steps {

		container('node') {
    
			echo "Maven Build"
	
			sh '''
			npm install
			
			'''
	
		}
	}
	
	
}






		}

 /*post {
	always { 
	 
	 cleanWs()	
	
	}
 
 }*/


}
