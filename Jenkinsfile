pipeline{
    agent{label 'jdk11-mvn3.8.4'}
    parameters{
        choies(choices: ['master', 'main ', 'real'], name: 'branches')
    }
    stages{
        stage('scm'){
            steps{
               git 'https://github.com/Madanalaanand/java11-examples.git'
            }
        }
        stage('build'){
            steps{
                sh '/usr/local/apache-maven-3.8.4/bin/mvn clean package'
            }
        }
    }
}