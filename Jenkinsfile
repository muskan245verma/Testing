pipeline {
    agent any 
    stages {
        stage('Checkout') { 
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: '965279af-cab6-4cf7-9829-4faa69c04d9c', url: 'https://github.com/muskan245verma/Testing.git']]]) }
        }
        stage('Build') { 
            steps {
                git branch: 'master', url: 'https://github.com/muskan245verma/Testing.git'
                bat 'python Lgame.py'
            }
        }
        stage('Test') { 
            steps {
                bat 'python test_Lgame.py'
                echo "Tested Successfully"
            }
        }
    }
}
