pipeline { 
  
   agent any

   stages {
   
     stage('build') { 
        steps { 
            sh 'echo "build application..."' 
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
