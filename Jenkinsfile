pipeline{
    agent{label 'jdk11-mvn3.8.4'}
    parameters {
        choice( name: 'branches', choices: ['master', 'main ', 'real'])
    }
    stages{
        stage('scm'){
            steps{
                 mail from: 'madanalaanand7@gmail.com',
                to : 'anand@gmail.com',
                subject: "status of the pipeline ${currentBuild.fullDisplayName}",
                body: "${env.BUILD_URL} has a result ${currentBuild.result}"
               git 'https://github.com/Madanalaanand/java11-examples.git'
            }
        }
        stage('build'){
            steps{
                mail from: 'madanalaanand7@gmail.com',
                to : 'anand@gmail.com',
                subject: "status of the pipeline ${currentBuild.fullDisplayName}",
                body: "${env.BUILD_URL} has a result ${currentBuild.result}"
                withSonarQubeEnv(installationName: 'SONAR_9.3', envOnly: true, credentialsId: 'SONAR_TOKEN'){
                    sh '/usr/local/apache-maven-3.8.4/bin/mvn clean package sonar:sonar'
                    echo "${env.SONAR_HOST_URL}"
    
                }
                
            }
        }
    }
        post{
            always{
                mail from: 'madanalaanand7@gmail.com',
                to : 'anand@gmail.com',
                subject: "status of the pipeline ${currentBuild.fullDisplayName}",
                body: "${env.BUILD_URL} has a result ${currentBuild.result}"

            }
        }
}