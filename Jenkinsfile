pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', URL: 'https://github.com/lavitha-p/pg8.git'
            }
        }

        stage('Build with Maven') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy with Ansible') {
            steps {
                sh 'ansible-playbook -i inventory.ini deploy.yml'
            }
        }
    }
}
