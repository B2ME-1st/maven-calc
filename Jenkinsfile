pipeline {
  agent any

  tools {
    maven 'Maven'  // or whatever you named it in Jenkins
  }

  environment {
    JAR_NAME = "springboot-calculator-1.0.0.jar"
  }

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/your-username/springboot-calculator.git'
      }
    }

    stage('Build') {
      steps {
        sh 'mvn clean package'
      }
    }

    stage('Deploy Locally') {
      steps {
        sh "nohup java -jar target/${JAR_NAME} &"
        echo "App deployed at http://localhost:8080"
      }
    }
  }
}
