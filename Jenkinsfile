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
        stage('deploy to dev') {
            steps {
                sh 'mkdir -rf /home/varun/.jenkins/workspace/Development/target'
                sh '/home/varun/Desktop/files/Dev_environment/apache-tomcat-9.0.86/bin/startup.sh'
                
'
            }
        }
    }
  post{
      always {
                     archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
            }

        }
}
