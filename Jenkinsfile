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

        stage('Run') 
        {
            when
			{
				expression { return !params.DRY_RUN }
			}
			steps 
            {
               sh 'python3 main.py >> output.txt'
            }
        }
    }
}
