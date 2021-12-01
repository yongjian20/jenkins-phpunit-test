pipeline {
	agent any
	stages {
		stage('Build') {
			sh 'composer install'
		}
		stage('Test') {
			steps {
                		sh './vendor/bin/phpunit --log-junit logs/unitreport.xml -c tests/phpunit.xml tests'
            		}
		}
	}
	post{
		always{
			junit testResults: 'logs/unitreport.xml'
		}
	}
}
