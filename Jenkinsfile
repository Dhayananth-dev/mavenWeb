pipeline{
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage("Build"){
            steps{
                sh '''
                mvn clean package 
                '''
            }
        }
        stage("Copy"){
            steps{
            steps {
                sh '''
                /opt/tomcat/bin/shutdown.sh || true
                rm -rf /opt/tomcat/webapps/cat
                rm -f /opt/tomcat/webapps/cat.war
                '''
            }
            }
        }
        stage("Run"){
            steps{
                sh '''
               /opt/tomcat/bin/startup.sh
                '''
            }
        }
    }
}