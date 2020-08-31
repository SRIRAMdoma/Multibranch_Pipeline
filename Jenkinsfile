pipeline{
  agent any
  environment{
     MS_BUILD = "C:\\Program Files (x86)\\Microsoft Visual Studio\\2019\\Enterprise\\MSBuild\\Current\\Bin\\MSBuild.exe"
	 CURL_CMD = "C:\\Program Files\\Git\\mingw64\\bin\\curl"
	 ARTIFACTORY_URL = "https://artifactory.solutions.corelogic.com/artifactory/edg_legacy_us-diabloplus-generic-snapshot-local/CFD/1.1/CFD.zip"
	 
  }
  parameters{
     
	  string(name:'BRANCH',defaultValue:'',description:'Enter the Branch to Build')
  }
  stages{
	stage('Checkout'){
       steps {
                git credentialsId: 'eaa25c99-1626-45aa-a026-cb5a4ceb3e64', url: 'https://github.com/corelogic/edg-diabloplus-cmas-xml.git', branch: """${params.BRANCH}"""
				
				}
   }   
  
	stage('Build-EoeProcess'){
	   steps{
			bat """ "${MS_BUILD}" -nologo -maxCpuCount EoeProcess.sln /t:Rebuild """
		}
	 }  
  }
}