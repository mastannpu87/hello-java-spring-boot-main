pipeline {
    environment {
        dockerRepo = "mastannpu87/hello-java-spring-boot"
        deploymentVersion = "master"
        dockerVersion = "latest"
    }
    agent any
    stages {
        stage ('Compile Stage') {
            steps {
                withMaven(maven : 'apache-maven-3.8.1') {
                    sh 'mvn clean compile'
                }
            }
        }
        stage ('Testing Stage') {
            steps {
                withMaven(maven : 'apache-maven-3.8.1') {
                    sh 'mvn test'
                }
            }
        }
        stage ('Install Stage') {
            steps {
                sh 'echo "mvn install"'
                //withMaven(maven : 'apache-maven-3.8.1') {
                  //  sh 'mvn install'
                // }
            }
        }
        stage ('Building Docker Image') {
            steps {
                // sh "docker tag ${dockerRepo}:${deploymentVersion} ${dockerRepo}:${dockerVersion}"
                sh "docker build -t ${dockerRepo}:${dockerVersion} ."
                sh "docker push ${dockerRepo}:${dockerVersion}"
                }
            }
    }
}