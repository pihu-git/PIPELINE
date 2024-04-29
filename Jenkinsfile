pipeline {
	agent any 
	
	parameters {
                choice choices: ['QA', 'UAT'], name: 'ENV'
        }
	
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '//home/khushi/Documents/Software-Downloads/apache-maven-3.9.6/bin/mvn install'
	                 }}
		stage('Deployment'){
		    steps {
			script {
			 if ( env.ENV == 'QA' ) {
        	                 sh 'cp target/PIPELINE.war /home/khushi/Documents/Software-Downloads/apache-tomcat-9.0.88/webapps'
        	echo "deployment has been COMPLETED on QA!"
			 }
			else ( env.ENV == 'UAT' ) {
    		                 sh 'cp target/PIPELINE.war /home/khushi/Documents/Software-Downloads/apache-tomcat-9.0.88/webapps'
    		echo "deployment has been done on UAT!"
			}
			}}}
		stage('Slack') {
	        steps {
			slackSend channel: '#project', color: 'good', message: 'Welcome to Slack-Notifications', teamDomain: 'Devops-slack', tokenCredentialId: 'bb7b909b-1695-4fdc-ada4-6c07e84aace1'slackSend baseUrl: 'https://hooks.slack.com/services/', channel: '#project', color: 'good', message: 'Welcome to Slack-Notifications', teamDomain: 'Devops-slack', tokenCredentialId: 'bb7b909b-1695-4fdc-ada4-6c07e84aace1'			       
		      }}
}}
