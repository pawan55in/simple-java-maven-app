pipeline{
  tools{
    maven 'mymaven'
  }
  agent any
  stages{
    stage ('Clone a repo')
     {
      steps {
        git 'https://github.com/pawan55in/simple-java-maven-app.git'
      }
     }
    stage ('Package the code')
     {
      steps{
        sh 'mvn clean package'
     }
    }
    stage ('Deploy the code')
     {
      steps{
        deploy adapters: [tomcat9(credentialsId: 'tomcat-id', path: '', url: 'http://localhost:9090/')], contextPath: null, war: '**/*.war'
   }
  }
 }
}
