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


    }
}
