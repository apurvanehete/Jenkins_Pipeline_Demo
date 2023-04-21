pipeline
{
	agent any 
	stages
	{ stage('Checkout') 
	  { steps 
	    { script 
		{ if (env.BRANCH_NAME == 'main') 
		  {checkout([$class: 'GitSCM', branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[credentialsId: '872f84d6-0500-4d2d-ab78-ea58896914e0', url: 'https://github.com/apurvanehete/Jenkins_Pipeline_Demo.git']]]) 
		  } 
		  else if (env.BRANCH_NAME == 'Python_Demo') 
		  { checkout([$class: 'GitSCM', branches: [[name: 'Python_Demo']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], 				userRemoteConfigs: [[url: 'https://github.com/example/repo.git']]]) 
		  } 
		} 
	    } 
	} 
	  stage('Build') 
		{ steps { script 
		  { if (env.BRANCH_NAME == 'master') 
			{ sh 'python master.py' }
		    else if (env.BRANCH_NAME == 'dev') 
			{ sh 'python dev.py' } } } } 
	  stage('Test') 
		{ steps { script 
		  { if (env.BRANCH_NAME == 'master') 
		      { sh 'python master_test.py' } 
		    else if (env.BRANCH_NAME == 'dev') 
		      { sh 'python dev_test.py' } } } } } 
}  
