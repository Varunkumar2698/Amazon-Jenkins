pipeline {
    agent any
    stages {

        stage('pull') {
            steps {
                git branch: 'main', url: 'https://github.com/PraveenKuber/Amazon-Jenkins.git'
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
        stage('deploy to development server') {
            steps {
                deploy adapters: [tomcat9(credentialsId: '9551387d-fc2a-401d-b340-7a8290e60ef6', path: '', url: 'http://localhost:8085/manager/html')], contextPath: 'Amazon-Jenkins', war: '**/*.war'
            }
        }
    }
  post{
      success {
          echo 'Deployment is successfull'
      }
    
              failure{
                   echo 'Deployment is failure'
               }

  }


}
