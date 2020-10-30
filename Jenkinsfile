pipeline {
  agent any
  stages {
    stage('Build/Shell script') {
      steps {
        sh 'mvn -f ssgsems/pom.xml -B -DskipTests clean package'
        archiveArtifacts(artifacts: '**/target/*.war', fingerprint: true)
        sh '''mkdir  /home/azureuser/buildoutput/${BUILD_NUMBER}
cp **/target/*.war /home/azureuser/buildoutput/${BUILD_NUMBER}'''
      }
    }

  }
}