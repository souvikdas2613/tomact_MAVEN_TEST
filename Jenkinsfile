pipeline
{
	agent any
    stages
    {
    	stage ('Initialize')
		{
			steps
			{
				echo "PATH = {$PATH}"
				echo "M2_HOME = {$M2_HOME}"
			}
		}
		
		stage ('Build')
		{
			steps
			{
				echo "HELLO WORLD"
				bat 'mvn clean package'
			}
		}
		
		stage ('post')
		{
			success
			{
				echo "Now archiving......."
				arhiveArtifacts artifacts : '**/*.war'
			}
		}
    }
}