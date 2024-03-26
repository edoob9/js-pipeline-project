pipeline {
	agent any
	environment {
		NEW_VERSION = '1.0.0'
		ADMIN_CREDENTIALS = credentials('admin_user_credentials')
	}
    
	parameters {
		string(name: 'VERSION', defaultValue: '', description: 'deployment version')
		choice(name: 'VERSION', choices: ['1.1.0','1.2.0','1.3.0'], description: '')
		booleanParam(name: 'executeTests', defaultValue: true, description: '')
	}

	stages {
		stage("build") {
			steps {
				echo 'building the applicaiton...'
				echo "building version ${NEW_VERSION}"
			}
		}
		stage("test") {
			steps {
				echo 'testing the applicaiton...'
			}
		}
		stage("deploy") {
			steps {
				echo 'deploying the applicaiton...'
				echo "deploying with ${ADMIN_CREDENTIALS}"
				sh 'printf ${ADMIN_CREDENTIALS}'
			}
		}
	}
}