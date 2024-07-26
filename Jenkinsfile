pipeline {
  agent any
  tools {
        maven "maven3.9.8"
  }  
  stages {
    stage('Checkout'){
      steps {
        sh "echo 'cloning the latest application version' "
        # Generate pipeline syntax for this using your Github repository and PAT
            }
        }
    stage('Test and Build'){
      steps {
        sh "echo 'running Unit-test-cases' "
        sh "echo 'testing must passed to build artifacts' "
        sh 'mvn clean package'
            }
        }
    stage('Deploy to Test Environment'){
      steps {
        sh "echo 'deploying to test environment' "
        sh 'docker build -t eavor-web-app:latest .'
        sh 'docker run -d -p 80:8080 eavor-web-app:latest'
            }
        }
    }
    post {
        always {
            junit '**/target/surefire-reports/*.xml'
        }
    }
}
