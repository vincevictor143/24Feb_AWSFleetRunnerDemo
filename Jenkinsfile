pipeline {
    agent any  // This will run the pipeline on any available agent

    stages 
    {
        stage('Pull the image') 
        {
            steps 
            {
                
                bat "docker pull attbatch1/dockerfinalimage"

            }
        }

        stage('Start the Grid') 
        {
            steps 
            {
                
                bat "docker-compose up -d hub chrome firefox"
            }
        }

        stage('Executing Cucumber TestCases') 
        {
            steps 
            {
                
                bat "docker-compose up cucumberbdd"
            }
        }

    }

    post 

    {
        always 
        {
            bat "docker-compose down"
        }
    }

}
