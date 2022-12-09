node {
   checkout scm
   stage 'Stage 1: sanity check'
   echo 'OK pipelines work in the test instance'
   stage 'Stage 2: steps check'
    def workflow_id = runOTFWorkflow(
        workflowPathName:'Soapexecute.json',
        workflowTimeout: '2000S',
        serverName:'defaultServer',
        jobDepth: 2,
        stepDepth: 3,
        dumpOnError: true
    )
    echo "We just ran The Squash Orchestrator with SOAPUI from GITHUB Projet2Autom"
	stage ('generate report') {

        dir("source") {

          publishHTML (target: [

              allowMissing: true,
              alwaysLinkToLastBuild: true,
              keepAll: true,
              reportDir: 'Workspaces',
              reportFiles: 'dependency-check-report.html',
              reportName: "Application-Dependency-Check-Report"

            ])
		}
			
	}
}