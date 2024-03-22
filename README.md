# JENKINSFILE-1

This file takes an input of only Submit and abort and it takes agent as any that is it
occupies an agent which we don't want.

# JENKINSFILE-2

This file has 2 stages one for input and other for output.
Now the input and output are segregated, i.e. input stage has none as the agent i.e. it will not take an builder,
but both the JENKINSFILE-1 and JENKINSFILE-2 has an issue that is it doesn't take desired input from the user.

# JENKINSFILE-3

Does that,
it takes desirable input from the user and prints it.

# JENKINSFILE-4

Clean code for jenkinsfile-3.

----------------------------------------------------------------------------

pipeline {
    agent none
    stages {
        stage('Input') {
            agent any
            ...
        }
    }
}

Top-Level agent Directive:

The agent none directive at the top level of the pipeline specifies that no specific agent should be allocated for the entire pipeline. This means that the stages defined within the pipeline will need to explicitly specify their own agents.
agent Directive within a Stage:

Within the stage('Input') block, the agent any directive is used to indicate that this specific stage (named "Input") can run on any available agent. In other words, it can execute on any available executor or node in the Jenkins environment.
By using agent none at the top level and agent any within the stage('Input'), this pipeline is configured to allow the "Input" stage to run on any available agent while ensuring that no specific agent is allocated for the entire pipeline. This provides flexibility in terms of agent allocation and allows the pipeline to adapt to the available resources in the Jenkins environment.

