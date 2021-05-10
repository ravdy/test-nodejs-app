pipeline { 
  
   agent any

   stages {
   
     stage('Install Dependencies') { 
        steps { 
           sh 'echo "testing application..."'//npm install
        }
     }
     
     stage('Test') { 
        steps { 
           sh 'echo "testing application..."'
        }
      }

         stage("Deploy nodejs application") { 
         steps { 
           sh 'echo "deploying application..."'
         }

     }
  
   	}

   }
