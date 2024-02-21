pipeline { 
  
   agent any

   stages {
   
     stage('Install Dependencies') { 
        steps { 
           sh 'echo "install Dependencies"'
           script{
             echo "Current branch: ${env.BRANCH_NAME}"
           }
        }
     }
     // stage('Git Clone') {
     //        steps {
     //            // Git clone step
     //            git branch: '*/stage', credentialsId: 'git-hub', url: 'your-repo-url'
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
