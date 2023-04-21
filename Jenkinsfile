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
		  { if (env.BRANCH_NAME == 'main') 
			{ sh 'python3 python_exe.py' }
		    else if (env.BRANCH_NAME == 'Python_Demo') 
			{ sh 'python3 Demo4.py' } } } } 
	  stage('Test') 
		{ steps { script 
		  { if (env.BRANCH_NAME == 'main') 
		      { echo 'Hello in Test main branch' } 
		    else if (env.BRANCH_NAME == 'Python_Demo') 
		      {echo 'Hello in Test Python_Demo branch' } } } } } 
}  
