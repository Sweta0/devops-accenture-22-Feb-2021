node {
    
    // Project Path Variables
    def project_path = "03-App-Code/petclinic-code"
    
    stage('Git CheckOut') {
     git branch: 'main', url: 'https://github.com/amitvashisttech/devops-accenture-22-Feb-2021.git'
     
    }
    
    dir(project_path) {
    
    stage('Maven - Clean') {
    sh 'mvn clean'
    }
    
    stage('Maven - Compile') {
    sh 'mvn compile'
    }
    
    stage('Maven - Test') {
    sh 'mvn test'
    }
    
    stage('Maven - Package') {
    sh 'mvn package'
    }
    
    stage('Archiva') {
     archive 'target/*.war'
    }
    
    stage('Stage Deployment') {
     sh 'docker-compose up -d --build'
    }
    
    }
}
