pipeline { 
  
   agent any

   stages {
   
     stage('Install Dependencies') { 
        steps { 
           sh 'sudo git --version' 
        }
     }
     
     stage('Test') { 
        steps { 
           sh 'echo "testing application..."'
        }
      }

         stage("Deploy application ASAP") { 
         steps { 
           sh 'echo "deploying application..."'
         }

     }
  
   	}

   }
