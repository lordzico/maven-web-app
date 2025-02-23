pipeline {  
    agent {
        label 'Ansible-Node'
    }    
    tools{
        maven "Maven-3.9.9"
    }
    stages {
        stage('Clone') {
            steps {
               git 'https://github.com/lordzico/JAVA-MAVEN-WEB-APP.git'
            }
        }
        stage('Build') {
            steps {
               sh 'mvn clean package'
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
