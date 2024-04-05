pipeline {
    agent any

    stages {
             stage('Git Checkout') {
            steps {
              git branch:'main', changelog: false, poll:false, url:'https://github.com/BhandariM/CI-CD-Pipeline.git'
            }
        }
        stage('Build') {
            steps {
                echo 'building the application..'
                // sh "npm build"
            }
        }
      stage('NPM Install') {
            steps {
                echo 'installing npm packages'
                // sh "npm install"
            }
        }
     stage('Test') {
            steps {
                echo 'testing the application..'
            }
        }

     stage('Deploy') {
            steps {
              echo 'deploying the application..'
            }
        }


    }
}