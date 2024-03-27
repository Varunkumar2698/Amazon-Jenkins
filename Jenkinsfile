pipeline {
    agent {
        label 'windowsagent'
    }
    environment {
        JAVA_HOME='C:\\Program Files\\Java\\jdk-17'
        MAVEN_HOME='C:\\Program Files\\Maven\\apache-maven-3.9.6'
    }
    tools {
       
        maven 'mvn381'
    }
    stages {
        stage('pull') {
            steps {               
                git branch: 'main', url: 'https://github.com/Varunkumar2698/Amazon-Jenkins.git'
            }
        }
        stage('compile') {
            steps {
                
                bat '"%MAVEN_HOME%\\bin\\mvn" compile'
            }
        }    
        stage('build') {
            steps {
                bat '"%MAVEN_HOME%\\bin\\mvn" clean install'
            }
        }
    }
}
