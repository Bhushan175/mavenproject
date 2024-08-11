pipeline   // comment: declarative pipeline always start with pipeline
{
   agent any  //run below stages on any executirs or build vm    
   stages   //(it contain all the stages)
    {
        stage('scm checkout') //stage name
        {
            steps {  git branch: 'master', url: 'https://github.com/Bhushan175/mavenproject.git' } //it tells jenkins what to do

        }
        stage('code compile')
        {
            steps { withMaven(globalMavenSettingsConfig: '', jdk: 'JDK_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true)
                {sh 'mvn compile'}
              }
        }
        
        stage('execute unit test framework')
         {
            steps { withMaven(globalMavenSettingsConfig: '', jdk: 'JDK_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true)
            {sh 'mvn test'} }
            
            
          }
        stage('execute build')
         {
            steps { withMaven(globalMavenSettingsConfig: '', jdk: 'JDK_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true)
            {sh 'mvn package'} }
            
            
          }
          stage('deploy to tomcat server')
          {
             steps {
              sshagent(['deploy-to-tomcat']) {
              sh 'scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@172.31.80.37:/usr/share/tomcat/webapps/'
              }
             }
          
         }

       stage('deploy to tomcat server')
          {
             input 'Do you apporve deployment?' ;
             steps {
              sshagent(['deploy-to-tomcat']) {
              sh 'scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@172.31.80.37:/usr/share/tomcat/webapps/'
              }
             }
          
         }
       
    }
}
