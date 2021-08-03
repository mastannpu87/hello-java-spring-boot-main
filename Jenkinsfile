pipeline {
    agent any

    stages {
        stage ('Compile Stage') {
            steps {
                withMaven(maven : 'apache-maven-3.8.1') {
                    sh 'mvn clean compile'
                }
            }
        }
        stage ('Compile Stage') {
            steps {
                withMaven(maven : 'apache-maven-3.8.1') {
                    sh 'mvn clean install'
                }
            }
        }
    post{
        always {
          cleanWs()            
        }
    }
  }
}