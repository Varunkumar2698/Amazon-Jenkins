pipeline {
    agent {
        label 'linuxwebsocket'
    }
    tools{
        maven 'mvn381'
    }
    stages {

        stage('pull') {
            steps {
                git url: 'https://github.com/Varunkumar2698/Amazon-Jenkins.git', branch: 'main', credentialsId: 'Github'
            }
        }
        stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }    
        stage('build') {
            steps {
                 sh 'mvn clean install'
            }
        }
    }
  }
