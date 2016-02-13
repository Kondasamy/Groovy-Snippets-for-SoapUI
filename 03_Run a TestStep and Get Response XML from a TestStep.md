# Run a Test Step & Get Response XML from a Test Step #

## Problem Statement: ##
In this scenario we could create a Groovy Script Test step within the test case where the targeted test step resides and run the below code.

## Resolution: ##
For this problem, we are going to write a script assertion in the test step and going to validate the specific variable/ header property with the expected value. In this context, we are going to validate the response header property - 'Content-Type'.

## Prerequisite: ##
1. Create a Groovy Script Test step within the test case where the test step resides
1. In the given code, the targeted test step's name should be replaced instead of **"Request 1"**
1. Paste the below code and run it

## Code Snippet ##
    //Run teststep with name - "Request 1" that lies within the testcase
    testRunner.runTestStepByName("Request 1")
    //Get the response XML from the the teststep name "Request 1"
    def responseXML = testRunner.testCase.getTestStepByName("Request 1").getHttpRequest().getResponseContentAsXml()
    log.info("Response value is: "+responseXML)
    //Get the request XML from the the teststep name "Request 1"
    def requestXML = testRunner.testCase.getTestStepByName("Request 1").getHttpRequest().getRequestContent()
    log.info("Request value is: "+requestXML)
    //Get the request Headers from the the teststep name "Request 1"
    def requestHeaders = testRunner.testCase.getTestStepByName("Request 1").getHttpRequest().getRequestHeaders()
    log.info("Request headers are: "+requestHeaders