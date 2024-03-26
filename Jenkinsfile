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
                git branch: 'main', changelog: false, credentialsId: 'Github', poll: false, url: 'https://github.com/Varunkumar2698/Amazon-Jenkins.git'
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
