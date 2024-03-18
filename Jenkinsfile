pipeline {
    agent any
    environment {
        TOMCAT_HOME= "/home/varun/Desktop/files/Dev_environment/apache-tomcat-9.0.86/"
        WAR_FILE= "Amazon-Jenkins.war"
"
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
                    sh "cp target/${WAR_FILE} ${TOMCAT_HOME}/webapps/"
                    sh "$TOMCAT_HOME/bin/startup.sh"
                }
            }
         }
            
        }
}
