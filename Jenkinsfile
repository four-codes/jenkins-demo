node {   
    stage('Checkout the dockefile from GitHub') {            
      git branch: 'main', credentialsId: 'git_credentials', url: 'https://gitlab.com/demo.git'        
    }       
    stage('Build the Image and Push to Azure Container Registry') {   
        docker build -t jjino/dome .
//       app = docker.build('testacr.azurecr.io/demo')                
//       withDockerRegistry([credentialsId: 'acr_credentials', url: 'https://testacr.azurecr.io']) {                
//       app.push("${env.BUILD_NUMBER}")                
//       app.push('latest')                
//      }        
    }        
}
