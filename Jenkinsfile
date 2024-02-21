pipeline { 
  
   agent any

   stages {
   
     stage('Install Dependencies') { 
        steps { 
           sh 'echo "install Dependencies"'
           script{
             echo "Current branch: ${env.BRANCH_NAME}"
             echo "Git repo: ${env.GIT_URL}"
           }
        }
     }
     stage('Git Clone') {
            steps {
                // Git clone step
                script{
                  // git branch: "${env.BRANCH_NAME}", credentialsId: 'git-hub', URL: "${env.GIT_URL}"
                  git branch: "${env.BRANCH_NAME}", credentialsId: 'git-hub', URL: "${env.GIT_URL}"

                }
            }
        }
     
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
