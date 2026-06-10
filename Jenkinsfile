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
                cp target/*.war  tomcat/webapps
                '''
            }
        }
        stage("Run"){
            steps{
                sh '''
                tomcat/bin/startup.sh
                '''
            }
        }
    }
}