#! groovy
@Library('roboshop-shared-library') _

// resposibilit to pass what type of application and component of this to the pipeline decission

def configMap = [
    application = "nodejsVM",
    component = "catalogue"
]

if (! evn.BRANCH_NAME.equalsIgnorecase(main)){
    pipelineDecission.decideiple(configMap)
}

elso {
    echo "This is PRODUCTION, deal with CR process"
}

