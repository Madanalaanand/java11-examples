pipeline{
    agent{label 'jdk11-mvn3.8.4'}
    stages{
        stage('scm'){
            steps{
               git 'https://github.com/Madanalaanand/java11-examples.git'
            }
        }
        stage('build'){
            steps{
                sh 'mvn clean package'
            }
        }
    }
}