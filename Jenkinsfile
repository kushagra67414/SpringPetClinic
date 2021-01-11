pipeline{
    agent{label 'master'}
    tools {
        maven 'M3'
    }
    stages{
        stage('Checkout'){
            steps{
                git branch: 'main' , url: 'https://github.com/kushagra67414/SpringPetClinic.git'
            }
        }
        stage('Build'){
            steps{
                bat 'mvn compile'
            }
        }
        stage('Test'){
            steps{
                bat 'mvn test'
            }
        }
        stage('Package'){
            steps{
                bat 'mvn package'
            }
        }
        stage('Deploy'){
            steps{
                sh 'java -jar /var/lib/jenkins/workspace/Declarative_petClinic/target/*.jar'
            }
        }
    }
}
