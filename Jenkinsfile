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
        stage ("Deployment")  {
               steps  {
                 bat  "del /q /s c:\\inetpub\\wwwroot\\myapp\\*"
                 bat  "xcopy /E /Y /I dist\\myApp\\browser\\* c:\\inetpub\\wwwroot\\myapp\\"
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
