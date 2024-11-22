pipeline {  
    agent any
    tools{
        maven "Maven_Home"
    }
    stages {
        stage('Clone') {
            steps {
               git 'https://github.com/ashokitschool/maven-web-app.git'
            }
        }
        stage('Build') {
            steps {
               bat 'mvn clean package'
            }
        }        
        stage('Create Image'){
            steps{
               steps {
                	script {
                		bat 'ansible-playbook task.yml'
                	}
                }
            }
        }
    }
}
