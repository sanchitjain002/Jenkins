pipeline{
    agent any
	parameters{
		choice(name:'Version', choices:['1.1.0','1.2.0','1.3.0'],description:'')
		booleanParam(name:'executeTest',defaultValue:true,description:'')
		string(name:'Environ',defaultValue:'',description:'deploying to this environment')
	}
	environment{
		NEW_VERSION='1.3.0'
	}
    stages{
        stage("build"){
			steps{
				echo "Building an application"
				echo "Version ${NEW_VERSION}"
				bat "python C:\Users\sanchit jain\Desktop\Jenkins\demo.py"
			}
		}
		stage("Test"){
			when{
				expression{
				BRANCH_NAME=='master'}
				expression{
				params.executeTest
				}
			}
			steps{
				echo "Testing an application"
			}
		}
		stage("Deploy"){
			steps{
				echo "Deploying an application"
				echo "Deploying version ${params.Version}"
				echo "Deploying in env ${params.Environ}"
			}
		}
        
    }    
}

