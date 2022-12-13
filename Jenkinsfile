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
            git branch:'main'; url:'https://github.com/Teja-Chittamuri/devops_CI_Project.git'
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
 
      }
    }
}
