pipeline 
{
    agent any

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
            steps 
            {
               sh 'python3 main.py'
            }
        }
    }
}
