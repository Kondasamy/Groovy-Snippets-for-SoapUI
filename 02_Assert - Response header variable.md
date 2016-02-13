# Assert - Response header variable #

## Problem Statement: ##
We face some situation, where we need to validate/ assert a particular header variable/ value in the response part of any SOAP/ REST request. 

## Resolution: ##
For this problem, we are going to write a script assertion in the test step and going to validate the specific variable/ header property with the expected value. In this context, we are going to validate the response header property - 'Content-Type'.

## Prerequisite: ##
1. Create a Groovy Script assertion within the test step
1. Modify the expected value for the 'Content-Type' header property in the highlighted part of the below script
1. Paste the below code and run it

## Code Snippet ##
    def appIdHeader = messageExchange.responseHeaders.get("Content-Type")
    
    if (appIdHeader != null && !appIdHeader.empty)
    	assert appIdHeader.get(0).contains("application/soap+xml")
    else
    	assert false