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
				echo "INITIALIZING CODE FILE............."
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
			steps
			{
				echo "Now archiving......."
				archiveArtifacts artifacts: '**/target/*.war'
			}
		}
		
		stage ('Deplay in Stage')
		{
			steps
			{
				build job : 'Deploy_by_Pipeline'
			}
		}
	}
}
