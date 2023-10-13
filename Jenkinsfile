pipeline{
  agent any
  tools{
    maven 'maven'
  }
  stages{
    stage("Clean un"){
      steps{
        deleteDir()
      }
    }
    stage("Clone repo"){
      steps{
        sh "git clone https://github.com/MohamedAmineDev/devops-tp2.git "
      }
    }
    stage("Generate backend image"){
      steps{
        dir("devops-tp2"){
          sh "mvn clean install"
          sh "docker build -t backend ."
        }
      }
    }
    stage("Run docker compose"){
      steps{
        dir("devops-tp2"){
          sh "docker compose up -d"
        }
      }
    }
  }
}
