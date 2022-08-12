node
{
 
  stage("CheckOutCodeGit")
  {
   git branch: 'main', credentialsId: '65fb834f-a83b-4fe7-8e11-686245c47a65', url: 'https://github.com/Afzalsr/AXYYA-DIGITAL-Assesment-LB1.git'
 }
 
 stage("Build")
 {
 nodejs(nodeJSInstallationName: 'nodejs15.2.1') {
        sh 'npm install'
    }
 }  
