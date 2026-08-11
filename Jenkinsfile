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
        timeout(time: 15, unit: 'MINUTES')
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'DEPLOY', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
                        echo "Hello ${params.PERSON}"
                        echo "Biography: ${params.BIOGRAPHY}"
                        echo "Toggle: ${params.TOGGLE}"
                        echo "Choice: ${params.CHOICE}"
                        echo "Password: ${params.PASSWORD}"
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

