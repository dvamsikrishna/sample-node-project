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
 
stage('NPM_INSTALL') {

	when { expression { params.ACTION == 'Install' } }

	steps {

		container('node') {
    
			echo "NPM Install Dependencies"
	
			sh '''
			npm install
			
			'''
	
		}
	}
	
	
}

stage('NPM_Build') {

	when { expression { params.ACTION == 'Build' } }

	steps {

		container('node') {
    
			echo "NPM Build"
	
			sh '''
			npm run build
			
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
