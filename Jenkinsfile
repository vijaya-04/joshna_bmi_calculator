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
               def output = sh 'mvn clean package'
               echo output
            }
        }        
        stage('Create Image'){
            steps{
               steps {
                	script {
                		sh 'ansible-playbook task.yml'
                	}
                }
            }
        }
    }
}
