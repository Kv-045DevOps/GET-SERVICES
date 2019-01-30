def buildResult
def paramss = ["GitHub/SRM-GET/test", "GitHub/SRM-UI/test", "GitHub/SRM-DB/test"]
properties([
    parameters([
        stringParam(
            defaultValue: 'v3.0', 
            description: '', 
            name: 'imageTag'),
        stringParam(
            defaultValue: '***', 
            description: '', 
            name: 'namespace')
    ])
])

        stage('Build and push Docker images') {
            def jobsss
	    
	            
		paramss.each{j -> jobsss = build job: "${it}", parameters: [[$class: 'StringParameterValue', name: "imageTag", 
        	                        value: "${params.imageTag}"]], wait: true}
	    
	    parallel jobsss
        }

