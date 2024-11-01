pipeline {
    agent { 
        node {
            label 'docker-agent-python' // Ensure this matches your Jenkins node label
        }
    }
    triggers {
        pollSCM '* * * * *' // Poll the SCM every minute
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                pip install -r requirements.txt // Install dependencies
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                python3 HelloWorld.py // Run your main script
                python3 HelloWorld.py --name=Brad // Test with argument
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Delivering....'
                sh '''
                echo "Doing delivery stuff.."
                '''
            }
        }
    }
}
