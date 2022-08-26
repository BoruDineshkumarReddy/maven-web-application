node{
  
   def mavenHome = tool name: "maven3.8.4" 
 stage ('checkoutcode') {
      git branch: 'development', credentialsId: 'd70720a2-175b-4ff7-b330-9de30ceac7a5', url: 'https://github.com/BoruDineshkumarReddy/maven-web-application.git' 
     
    }
 stage ('Build'){
    sh "${mavenHome}/bin/mvn clean package "
 }
 
 stage ('sonarqube report'){
     sh "${mavenHome}/bin/mvn sonar:sonar"
 }
 stage ('Upload artifact to nexus'){
     sh "${mavenHome}/bin/mvn deploy"
 }
}   
