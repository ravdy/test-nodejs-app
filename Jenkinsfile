pipeline { 
  
     agent {
        label 'java-node'
    }

   stages {
   
     stage('Install Dependencies') { 
        steps { 
           sh 'npm install' 
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

         stage("apply successful") { 
         steps { 
           sh 'echo "Successfully deployed new version..."'
         }

     }
  
   	}

   }
