pipeline {
    agent {
        label 'windowsagent'
    }
    environment {
        JAVA_HOME='C:\\Program Files\\Java\\jdk-17'
    }
    tools {
        // Define Maven tool named 'maven-3.8.1'
        // Make sure 'maven-3.8.1' is configured in Jenkins under Global Tool Configuration
        maven 'mvn381'
    }
    stages {
        stage('pull') {
            steps {
                // Git checkout
                git branch: 'main', url: 'https://github.com/Varunkumar2698/Amazon-Jenkins.git'
            }
        }
        stage('compile') {
            steps {
                // Compile using Maven
                bat '"%MAVEN_HOME%\\bin\\mvn" compile'
            }
        }    
        stage('build') {
            steps {
                // Clean and install using Maven
                bat '"%MAVEN_HOME%\\bin\\mvn" clean install'
            }
        }
    }
}
