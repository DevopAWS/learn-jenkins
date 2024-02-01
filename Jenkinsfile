pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
        environment { 
             GREETING = 'Hello Jenkins'
    }    

    options {
        timeout(time: 1, unit: 'HOUR') 
        disableConcurrentBuilds()
    }
    // build
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                sh """
                    echo " Here I Wrote Shell Script"
                    echo "$GREETING"
                    sleep 10
                """
            }
          }
     }
        // post build
        post { 
            always { 
                echo 'I will always say Hello again!'
            }
            failure { 
                echo 'this runs when pipeline is failed,used genarally to some send alerts'
            }
            success { 
                echo 'I will say hello when pipeline success'
            }
        }
    }