@Library('Mylib')_
pipeline
{
    agent any
    stages
    {
        stage('download')
        {
            steps
            {
                script
                {
                  cicd.gitDownload("maven")  
                }
            }
        }
        stage('build')
        {
            steps
            {
                script
                {
                    cicd.buildArtifact()
                }
            }
        }
        stage('deploy')
        {
            steps
            {
                script
                {
                    cicd.Deploy("DeclarativePipeline1","172.31.1.147","testapp")
                }
            }
        }
        stage('testing')
        {
          steps
          {
              script
              {
                  cicd.gitDownload("FunctionalTesting")  
                  cicd.runSelenium("DeclarativePipeline1")
              }
          }
        }
        stage('delivery')
        {
            steps
            {
                script
                {
                    cicd.Deploy("DeclarativePipeline1","172.31.9.253","prodapp")
                }
            }
        }
    }
}

