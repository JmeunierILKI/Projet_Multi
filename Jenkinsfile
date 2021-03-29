pipeline {

  agent {
    label 'Linux'
  }

  stages {
     
    stage('Tests unitaires') {
    
      steps {
        sh 'mvn test'
      }
  
    }

    stage('Compilation') {
    
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
      
    }
    
    stage ('Publication du binaire') {

      steps {
        sh "curl -u admin:xao672JM --upload-file target/*jar 'http://10.10.20.31/repository/depot_test/test_maven-1.0-SNAPSHOT.jar'"
      }

    }
    
  }
  
}