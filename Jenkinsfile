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
		container('maven') {
	
				echo "Unit-Test"
	
				 sh "npm test"
	
		}
	}
}
 
stage('Maven_Build') {

	when { expression { params.ACTION == 'Build' } }

	steps {

		container('maven') {
    
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
