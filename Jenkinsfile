pipeline {
	agent any
	stages {
		stage('Build') {
			steps {
				sh 'phpunit --log-junit results/phpunit/phpunit.xml -c tests/phpunit.xml'
			}
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
