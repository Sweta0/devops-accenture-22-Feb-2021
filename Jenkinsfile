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
    
    stage('Archive Artifacts') {
     archive 'target/*.war'
    }
    
    stage('Deployment to Staging Env') {
     sh 'docker-compose up -d --build'
    }
    
    stage('Getting Ready for Ansible') {
     sh "echo \'<h1> JENKINS TASK BUILD ID: ${env.BUILD_DISPLAY_NAME}</h1>\' > ../../06-Ansible/04-Roles/roles/petclinic/files/jenkins.html"
     sh "cp -rf target/*.war ../../06-Ansible/04-Roles/roles/petclinic/files/"
    }
    
   
    stage('Ansible Deployment') {
     sh "cd ../../06-Ansible/04-Roles/; ansible-playbook petclinic.yaml"
    }

    }
}
