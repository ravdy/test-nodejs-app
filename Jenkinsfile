pipeline { 
  
   agent any

   stages {
   
     stage('Install Dependencies') { 
        steps { 
           sh 'echo "Install Dependencies ${GIT_URL}"'
           script{
             echo "Current branch: Dunkins_${env.BRANCH_NAME}_env"
             echo "Git repo: ${env.GIT_URL}"
           }
        }
     }
     stage('Checkout') {
            steps {
                // Automatically checks out the source code for the branch that triggered the build
                checkout scm
            }
        }
     
     // stage('Git Clone') { 
     //        steps {
     //            // Git clone step
     //            script{
     //              // git branch: "${env.BRANCH_NAME}", credentialsId: 'git-hub', URL: "${env.GIT_URL}"
     //              git branch: "${env.BRANCH_NAME}", credentialsId: 'git-hub', URL: 'https://github.com/ashirwad8858/test-nodejs-app-jenkins-pipline.git'

     //            }
     //        }
     //    }
     
     stage('Test') { 
        steps { 
           sh 'echo "testing application..."'
        }
      }

         stage("Deploy application") { 
         steps { 
           sh 'echo "deploying application..."'
         }

     }
  
   	}

   }
