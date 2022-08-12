node
{
 
  stage("CheckOutCodeGit")
  {
   git branch: 'main', credentialsId: '65fb834f-a83b-4fe7-8e11-686245c47a65', url: 'https://github.com/Afzalsr/AXYYA-DIGITAL-Assesment-LB1.git'
 }
 
 stage("Build")
 {
 nodejs(nodeJSInstallationName: 'nodejs14') {
        sh 'npm install'
    }
  stage("Docker Build"){
  sh "docker build -t dockerafzal123/nodejs14 ."
 }
  stage("docker login and push"){
  withCredentials([string(credentialsId: 'DOKCER_HUB_PASSWORD', variable: 'DOKCER_HUB_PASSWORD')]) {
          sh "docker login -u dockerafzal123 -p ${DOKCER_HUB_PASSWORD}"
  }
   sh "docker push dockerafzal123/nodejs14"
 }
  stage("Deploy To Kuberates Cluster"){
   
  sh "kubectl apply -f nodejs.yml"
   
 }
  
}
