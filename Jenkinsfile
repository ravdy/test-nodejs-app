pipeline { 
  agent any
  
  stages {
   
     stage('Install Dependencies') { 
        steps { 
           sh 'npm install' 
        }
     }
     
     stage('Test') {
       when {
         beforeAgent true
         anyof {
           branch 'develop'; branch 'prod'
              }
       }
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
