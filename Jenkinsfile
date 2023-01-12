pipeline {
    agent any
    environment {
      PROJECT_NAME = "Jenkins multibranch pipeline "
      OWNER_NAME   = "Nemo"
    }

    stages {
        stage('1-Build') {
            steps {
                echo "Start of Stage Build..."
                echo "Building......."
                echo "End of Stage Build..."
            }
        }
        stage('1.5-Build') {
            steps {
                echo "lets play in python"
                sh '''#!/usr/bin/python3

for i in range(1,3):
    print("i = " + str(i))
print("done")'''
                echo "End of Stage Build..."
            }
        }
        stage('2-Test') {
            steps {
                echo "Start of Stage Test..."
                echo "Testing......."
                echo "Privet ${PROJECT_NAME}"
                echo "Owner is ${OWNER_NAME}"
                echo "End of Stage Build..."
            }
        }
        stage('3-Deploy') {
            steps {
                echo "Start of Stage Deploy..."
                echo "Deploying......."
                sh "ls -la"
                sh '''
                   echo "Line1"
                   echo "Line2"
                '''
                echo "End of Stage Build..."
            }
        }
        stage('4-Celebrate') {
            steps {
                echo "CONGRATULYACIYA!"
            }
        }	
    }
    post {
        always {
            echo "always post"
        }
        success {
            echo "success post"
        }
        failure {
            echo "failure post"
        }
    }
}
