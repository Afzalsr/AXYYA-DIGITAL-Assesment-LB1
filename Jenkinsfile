node
{
 
  stage("CheckOutCodeGit")
  {
   git branch: 'master', credentialsId: '65fb834f-a83b-4fe7-8e11-686245c47a65', url: 'https://github.com/bhaskar0504/node-js-application.git'
 }
 
 stage("Build")
 {
 nodejs(nodeJSInstallationName: 'nodejs15.2.1') {
        sh 'npm install'
    }
 }  
