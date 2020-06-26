pipeline {
  agent any
  stages 
    {
      stage('Sonar Analysis') {
    when (BRANCH_NAME != 'master') {
        echo 'Excecuted only on master branch.'
    }
}
    stage('Compile') {
      steps {
        bat 'mvn compile'
      }
    }
      stage('Package') {
      steps {
        bat 'mvn package'
      }
    }
      stage('Install') {
      steps {
        bat 'mvn install'
      }
    }
      stage('Artifacts to nexus') {
      steps {
        bat 'mvn deploy'
      }
    }
      stage('Deplot to tomcat') {
      steps {
        bat 'mvn tomcat7:deploy'
      }
    }
    
  }
}
