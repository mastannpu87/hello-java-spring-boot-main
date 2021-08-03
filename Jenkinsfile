pipeline {
    agent {
        dockerfile true
    }
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
        // stage ('Install Stage') {
        //     steps {
        //         withMaven(maven : 'apache-maven-3.8.1') {
        //             sh 'mvn install'
        //         }
        //     }
        // }
        // stage ('Docker Build') {
        //     steps {
        //         script {
        //         def customImage = docker.build("mastannpu87/hello-java-spring-boot:latest")
        //         customImage.push()
        //             }
        //         }
        //     }
        }
}