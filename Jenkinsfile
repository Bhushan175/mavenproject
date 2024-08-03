pipeline   // comment: declarative pipeline always start with pipeline
{
   agent any  //run below stages on any executirs or build vm    
   stages   //(it contain all the stages)
    {
        stage('scm checkout') //stage name
        {
            steps { echo git 'https://github.com/Bhushan175/mavenproject.git' } //it tells jenkins what to do
        }
    }
}