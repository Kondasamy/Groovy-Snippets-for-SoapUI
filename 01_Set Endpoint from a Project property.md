# Set Endpoint from a Project property #

## Problem Statement: ##
We might face some scenarios, where we need to change endpoints each and every release/ cycle. If we need to do it manually, we usually traverse each and every test step in the project and we modify the endpoint. This becomes worst if we have more test steps.

## Resolution: ##
In order to solve this problem, we could create a Project Property where we can update our endpoint for the particular release/ cycle. Setting the endpoint of each test steps referencing the project property would solve this issue.

## Prerequisite: ##
1. Create a Groovy Script Teststep inside any testcase of the project
1. Create a Project Property called "Endpoint" (matching the highlighted statement in Code Snippet)
1. Paste the below code and run it

## Code Snippet ##
    //Refer a Project property "Endpoint" where we store actual endpoint
    //We could even try directly placing the endpoint URI here
    def endpoint = '${#Project#Endpoint}'
    testRunner.testCase.testSuite.project.testSuites.each
    {
    suit ->
    suit.getValue().testCases.each
    {
    q1->
    q1.getValue().testSteps.each
    {
     it->
     if (it.getValue().config.type.equals("restrequest"))
     {
     it.getValue().getHttpRequest().setEndpoint(endpoint); 
     }
     }
    }
    }
    log.info("Done")