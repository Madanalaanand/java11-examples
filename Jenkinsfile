pipeline{
    agent{label 'jdk11-mvn3.8.4'}
    stages{
        stage('scm'){
            step{
               git 'https://github.com/Madanalaanand/java11-examples.git'
            }
        }
        stage('build'){
            step{
                sh 'mvn clean package'
            }
        }
    }
}