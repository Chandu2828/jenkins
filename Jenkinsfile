pipeline {
    agent {
        node {
            label 'ROBOSHOP'  
        }
    }
    environment {
        COURSE = "Jenkins"
    }
    options {
        disableConcurrentBuilds() // to queue a build when there's already an executing build of the pipeline 
        timeout(time: 15, Unit: 'MINUTES')
    }
// when executing this pipeline jenkins will check this label
// then it will launch the agent and the build the pipeline in that agent
// Build 
    stages {
        stage('Build') {
            steps {
                script {
                    sh """
                        echo "Building"
                        echo "Course is: ${COURSE}"
                        sleep 5
                    """
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh """
                        echo "Testing"
                    """
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    sh """
                        echo "Deploying"
                    """
                }
            }
        }
    }

    post {
        always {
            echo 'I will always say hello again!'
        }
        success {
            echo 'I will run when success'
        }
        failure {
            echo 'I will run when it is failed'
        }
    }
}

// Hybird scrpit i.e., comibination of declarative and script


/* pipeline {
    agent any 

    stages {
        stage('Build') {
            steps {
                script {
                    sh """
                        echo "Building"
                    """
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh """
                        echo "Testing"
                    """
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    sh """
                        echo "Deploying"
                    """
                }
            }
        }
    }
}
 */

