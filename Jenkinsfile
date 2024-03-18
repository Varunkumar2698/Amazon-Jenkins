pipeline {
    agent any
    environment {
        TOMCAT_HOME= "/home/varun/Desktop/files/Dev_environment/apache-tomcat-9.0.86"
       
    }
    stages {

        stage('pull') {
            steps {
                git branch: 'main', url: 'https://github.com/PraveenKuber/Amazon-Jenkins.git'
            }
        }    
        stage('build') {
            steps {
                 sh 'mvn clean install'
            }
        }
        stage('test') {
            steps {
                 sh 'mvn clean install -DSkiptests=true'
            }
        }
        stage('deploy to development server') {
            steps {
                script {
                    sh "$TOMCAT_HOME/bin/shutdown.sh"
                    sh "mkdir /home/varun/.jenkins/workspace/Develpment/target"
                    sh "cp /home/varun/.jenkins/workspace/Development/target/*.war ${TOMCAT_HOME}/webapps/"
                    sh "$TOMCAT_HOME/bin/startup.sh"
                }
            }
         }
            
        }
}
