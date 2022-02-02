pipeline{
    agent{label 'jdk11-mvn3.8.4'}
    parameters {
        choice( name: 'branches', choices: ['master', 'main ', 'real'])
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
        stage('archive'){
            steps{
                archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
            }
        }
        stage('publish test reports'){
            steps{
                junit '**/TEST-*.xml'
            }
        }
    }
}