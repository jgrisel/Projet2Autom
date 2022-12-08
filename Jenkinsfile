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
    echo "We just ran The Squash Orchestrator with Robot template test from GITLAB Squashautom"
}