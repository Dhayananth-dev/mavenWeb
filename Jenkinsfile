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
                sh '''
                /opt/tomcat/bin/shutdown.sh || true
                sleep 5
                rm -rf /opt/tomcat/webapps/cat
                rm -f /opt/tomcat/webapps/cat.war
                cp target/*.war  /opt/tomcat/webapps
                '''
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