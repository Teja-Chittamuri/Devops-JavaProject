pipeline
{
  agent any
    tools
    {
      maven "maven"
      jdk "openjdk8"
    }
    stages
    {
      stage('fetch code from github')
      {
         steps{
            git branch:'vp-rem'; url:'https://github.com/Teja-Chittamuri/vprofile-project-Devops.git'
        }
      }
      stage('Build the artifact')
      {
        steps{
          sh 'mvn clean install -DskipTests'
        }
        post{
          success{
            echo 'Now Arhchiving it....'
            archiveArtifact artifacts: '**/*.war'
          }
        }
      }
      stage('unit test')
      {
        steps{
          sh 'mvn test'
        }
 
