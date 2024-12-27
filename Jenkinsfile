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
            }
}

