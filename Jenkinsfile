pipeline 
{
    agent any
	
	parameters
	{
		 booleanParam(
            name: 'DRY_RUN',
            defaultValue: false,
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
        
        stage('Set DRY_RUN')  //change dry_run for test
        {
            steps
            {
                script
                {
                    env.DRY_RUN = 'true' 
                }
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
