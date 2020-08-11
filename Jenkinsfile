pipeline {
    agent any

    stages {
        stage('list repo files') {
            steps {
               script{
                 sh "ls"
               }
            }
        }
        stage('show working directory') {
            steps {
               script{
                 sh "pwd"
               }
            }
        }
        stage('Creating build') {
            steps {
               script{
                 sh "./gradlew clean build"
               }
            }
        }
        stage('list build contents') {
            steps {
               script{
                 sh "ls build/libs"
               }
            }
        }
       
        stage('copy build file to docker context') {
            steps {
               script{
                 sh "sudo cp /var/lib/jenkins/workspace/full1/build/libs/spring-boot-with-prometheus-0.1.0.jar DOCKER/"

               }
            }
        }
        stage('bild docker image and push to dockerhub') {
            steps {
               script{
                 sh "cd DOCKER ;sudo docker build -t narendar414/phpandapache:v_${BUILD_NUMBER} ."
                  sh "sudo docker push narendar414/phpandapache:v_${BUILD_NUMBER}"

               }
            }
        }


    }
}
