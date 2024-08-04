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
            steps steps { withMaven(globalMavenSettingsConfig: '', jdk: 'JDK_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) 
            
            {sh 'mvn test'}
        }
    }

}