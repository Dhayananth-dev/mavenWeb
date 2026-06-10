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