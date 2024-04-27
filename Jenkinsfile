pipeline {
	agent any 
	
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/khushi/Documents/Software-Downloads/apache-maven-3.9.6'
	                 }}
		stage('Deployment'){
		   steps {
		          sh 'cp target/PIPELINE.war /home/khushi/Documents/Software-Downloads/apache-tomcat-9.0.88/webapps'
			}}	
}}
