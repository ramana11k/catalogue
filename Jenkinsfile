#!groovy
@Library('roboshop-shared-library') _

// resposibilit to pass what type of application and component of this to the pipeline decission

def configMap = [
    application = "nodejsVM",
    component = "catalogue"
]

if( ! env.BRANCH_NAME.equalsIgnoreCase('main')){
    pipelineDecission.decidePipeline(configMap)
}
else{
    echo "This is PRODUCTION, deal with CR process"
}

