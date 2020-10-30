pipeline {
    environment {
        registry = 'thigskillsassessment/catgifs'
        registryCredential = 'jenkinsPushToDockerHub'
        imageTag = "${BRANCH_NAME}-${BUILD_ID}"
    }

    agent any

    options {
        disableConcurrentBuilds()
        buildDiscarder(logRotator(numToKeepStr: '15'))
    }

    stages {
        stage('Print Env') {
            steps {
                sh 'printenv | sort'
            }
        }

        stage('Build') {
            steps {

            }
        }

        stage('Publish') {
            steps {
                
            }
        }

    }
}
