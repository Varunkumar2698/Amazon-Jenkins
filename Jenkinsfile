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
        stage('deploy to dev environment') {
            steps {
                archieveArtifacts artifacts: 'target/*.war', followSymlinks: false
                
                

            }
        }
    }
  post{
      success{
       sh 'echo "success in the deployment"'
   }
    
  failure{
       sh 'echo "Failure in the deployment"'
   }

  }


}
