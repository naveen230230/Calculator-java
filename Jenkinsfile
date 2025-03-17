pipeline{
    agent {label 'build'}
    stages{
       stage('Git Checkout Stage'){
            steps{
                git branch: 'master', url: 'https://github.com/sudheer76R/Calculator-java.git'
            }
         }        
       stage('Build Stage'){
            steps{
                sh 'mvn clean install'
            }
         }
        stage('SonarQube Analysis Stage') {
            steps{
                withSonarQubeEnv('calculator-java-pipeline') { 
                    sh "mvn clean verify sonar:sonar"
                }
            }
        }
    }
}
