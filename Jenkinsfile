pipeline {
    agent any
    environment{
        ENV = 'QA'
        SERVER_CREDS = credentials('my-pipeline')
    }
parameters{
    choice(name:'VERSION', choices:['1.1', '1.2', '1.3'], description:'')
    booleanParam(name:'executeTest', defaultValue:true, description:'')
}
    stages {
             stage('Git Checkout') {
            steps {
              git branch:'main', changelog: false, poll:false, url:'https://github.com/BhandariM/CI-CD-Pipeline.git'
            }
        }
        stage('Build') {
            steps {
                echo 'building the application..'
                     echo "building ${ENV}"
                    //  sh " ${ENV}"
            }
        }
      stage('NPM Install') {
            steps {
                echo 'installing npm packages'
                // sh "npm install"
            }
        }
     stage('Test') {
        when{
            expression{
                parameters.executeTest
            }
        }
            steps {
                echo 'testing the application..'
            }
        }

     stage('Deploy') {
            steps {
              echo 'deploying the application..'
                     sh "${SERVER_CREDS}"
         
            }
        }


    }
}