def dockerImage

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
                script {
                    dockerImage = docker.build("${registry}:${imageTag}")
                }
            }
        }

        stage('Publish') {
            steps {
                script {
                    docker.withRegistry( '', registryCredential ) { 
                        dockerImage.push() 
                        dockerImage.push("latest") 

                    }
                }
            }
        }
    }
}
