pipeline {
    agent any
	tools { 
		maven 'mvn' 
		jdk 'jdk8' 
	}
    stages {
        stage('build') {
            steps {
                script {
					sh "mvn clean install"
                }
            }
        }
        stage('deploy') {
            steps {
			deploy adapters: [tomcat8(url: 'http://54.147.132.251:8080', 
									  credentialsId: 'tomcat')], 
							 war: '**/*.war',
							 contextPath: 'myapp'
            }
        }
    }
}
