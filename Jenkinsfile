pipeline {
    agent any
    tools {
        nodejs "Nodejs"
    }
    stages {
        stage ( "Checkout") {
            steps {
                checkout scm
            }
        }
        stage ( "install pacakges") {
            steps {
               bat  "npm ci"
            }
        }
        stage ("test") {
            steps {
                   // bat "npx ng text --no-watch --no-progress --browser=Chromeheadless"
                 echo "testing"
                 }
        }
        stage ("build") {
            steps {
                    bat "npx ng build --configuration production"
                }
        }
    }
    post {
       success {
            echo "Angular application build successfully"
       }
        failure {
            echo "Build Failed"
        }
    }
}
