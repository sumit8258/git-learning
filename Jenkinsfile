pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
		checkout scm
	    }
	}
	stage('Build') {
	    steps {
		sh '/home/gamut/Downloads/apache-maven-3.6.1/bin/mvn install'
	}
	    }
	stage('Deployment') {
	    steps {
		sh 'sshpass -p "sumit" scp target/gamutkart.war gamut@172.17.0.4:/home/sumit/Download/apache-tomcat-8.5.38/webapps'
		sh 'sshpass -p "sumit" ssh gamut@172.17.0.4 "JAVA_HOME=/home/sumit/Download/jdk1.8.0_151" "/home/gamut/Distros/apache-tomcat-8.5.38/bin/startup.sh"'
	    }
	}

    }
}
