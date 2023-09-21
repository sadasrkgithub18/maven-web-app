node{

    stage('Clone repo'){
       git branch: 'main', credentialsId: '50137803-2c55-4259-9634-6054953641c2', url: 'https://github.com/sadasrkgithub18/maven-web-app.git'
    }
    
    stage('Maven Build'){
        def mavenHome = tool name: "Maven-3.9.4", type: "maven"
        def mavenCMD = "${mavenHome}/bin/mvn"
        sh "${mavenCMD} clean package"
    }
    
    stage('SonarQube analysis') {       
        withSonarQubeEnv() {
       	sh "mvn sonar:sonar"    	
    }
         
}
}
