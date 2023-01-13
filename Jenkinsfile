pipeline {
    agent any
    environment {
      PROJECT_NAME = "Jenkins multibranch pipeline "
      OWNER_NAME   = "Nemo"
      CURENT_VERSION = "0.0.1"
      CREDZ=credentials('154cec6d-0282-4194-9313-cd4a65e6d20c')
    }

    stages {
        stage('1-Build') {
            steps {
                echo "Start of Stage Build..."
                echo "Building......."
                sh 'date'
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
            when {
                expression {
                   BRANCH_NAME == 'master' 
                }
            }
            steps {
                echo "Start of Stage Test..."
                echo "Testing......."
                echo "Privet ${PROJECT_NAME}"
                echo "Owner is ${OWNER_NAME}"
                echo "Version \" ${CURENT_VERSION}"
                echo 'Version \' ${CURENT_VERSION}'
                echo "End of Stage Build..."
            }
        }
        stage('3-Deploy') {
            steps {
                echo "Start of Stage Deploy..."
                echo "Deploying......."
                echo "credz = ${CREDZ}"
                sh "echo "credz = ${CREDZ}"

                //withCredentials([usernamePassword(credentialsId: 'amazon', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
/*
                withCredentials([
                    usernamePassword(credentialsId: '154cec6d-0282-4194-9313-cd4a65e6d20c', usernameVariable: USER, passwordVariable: PASSWD)
                ]) {
                    sh "echo \"Creds are: USER = ${USER} PASSWD = ${PASSWD}\""
                }
*/
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
