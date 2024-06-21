pipeline {
	agent {
		label {
			label "built-in"
			customWorkspace "/mnt/test"
		}
	}
	tools {
		maven 'maven'
	}
	stages {
		stage ("Maven") {
			steps {
				sh 'rm -rf /root/.m2/repository'
				sh 'mvn clean package'
			}
		}
		stage ("Copy_war") {
			steps {
				sh "scp -r use.pem target/LoginWebApp.war ec2-user@ec2-13-234-59-134.ap-south-1.compute.amazonaws.com://root/server/apache-tomcat-9.0.90/webapps"
			}
		}
	}}

/*pipeline {
agent {
label {
		label "built-in"
		customWorkspace "/data/project-myapp"
		
		}
		}
		
	stages {
		
		stage ('CLEAN_OLD_M2') {
			
			steps {
				sh "rm -rf /home/saccount/.m2/repository"
				
			}
			
		}
	
		stage ('MAVEN_BUILD') {
		
			steps {
						
						sh "mvn clean package"
			
			}
			
		
		}
		
		stage ('COPY_WAR_TO_Server'){
		
				steps {
						
						sh "scp -r target/LoginWebApp.war saccount@10.0.2.51:/data/project/wars"

						}
				
				}
	
	
	
	}
		
}*/
