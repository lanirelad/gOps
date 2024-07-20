pipeline 
{
    agent any
	
	parameters
	{
		 booleanParam(
            name: 'DRY_RUN',
            defaultValue: true,
            description: 'Whether to run stage Run or not'
         )
	}
	
    stages 
    {
        stage('Fetch From Github') 
        {
            steps 
            {
                echo 'Fethcing code from github'
                git branch: 'main', url: 'https://github.com/lanirelad/jenkins01HW.git'
            }
        }

        stage('Debug') 
        {
            steps 
            {
                script 
                {
                    echo "DRY_RUN parameter value: ${params.DRY_RUN}"
                }
            }
        }

        stage('Run') 
        {
            when
			{
				expression {"${params.DRY_RUN}" == "false"} 
			}
			steps 
            {
               sh 'python3 main.py >> output.txt'
            }
        }
    }
}
