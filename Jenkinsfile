pipeline {
    agent any
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
                sh 'mvn test'
            }
        }
    }
  post{
      always {
                     archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
            }

        }
}
