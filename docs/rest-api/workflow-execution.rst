Workflow Execution REST API
============================

Overview
--------
 
The Workflow Execution REST API's, allow you to execute Workflows, get results etc.

Below are the various Workflow Execution API's available in Sparkflows

They should be executed after you have logged into Sparkflows

Execute a Workflow
------------------

It executes a given Workflow.

It returns the workflow execution id::

  curl -v -i -H "Accept:application/json" -H "Content-Type: application/json" -H "workflowId:1" -X POST -b /tmp/cookies.txt -d '{ "userName": "admin", "userId": 1, "sparkConfig": "", "libJarsList": [], "emailOnFailure": "", "emailOnSuccess": "" }' localhost:8080/workflowexecuterest


Get Analysis Flow Executions
----------------------------

Returns the list of Executions for the logged in user::

  curl -i --header "Accept:application/json" -X GET -b /tmp/cookies.txt localhost:8080/allWorkflowExecutions -b /tmp/cookies.txt

View execution result of a given execution
------------------------------------------

AnalysisFlowExecutionId = 79

Type = 2::

  curl -i --header "Accept:application/json" -H "Content-Type:application/json" -H "analysisFlowExecutionId:79" -H "type:2" -X GET -X GET -b /tmp/cookies.txt localhost:8080/viewExecutionResult
  
View executions of a Workflow
------------------------------
 
Return the list of Executions for given Analysis Flow Id.

workflowId = 81::

  curl -X GET --header 'Accept: text/html' --header 'workflowId: 81' 'http://localhost:8080/workflowExecutions' -b /tmp/cookies.txt
  
Stop Executing a Workflow
-------------------------
 
Return the list of Executions for given Analysis Flow Id.

Workflow Execution Id = 1::

  curl -X GET --header 'Accept: text/html' --header 'workflowExecutionId: 1' 'http://localhost:8080/stopWorkflowExecution' -b /tmp/cookies.txt
  
View Spark Log of a workflow execution
--------------------------------------
 
Return the logs of a given workflow execution

Workflow Execution Id = 81::

  curl -X GET --header 'Accept: text/html' --header 'workflowExecutionId: 81' 'http://localhost:8080/viewLogs' -b /tmp/cookies.txt
  
Consume the message sent from YarnRestWorkflowContext
-----------------------------------------------------
 
jobId=1

message=test::

  curl -X POST --header 'Content-Type: application/json' --header 'Accept: text/plain' 'http://localhost:8080//messageFromSparkJob ?jobId=1&message=test' -b /tmp/cookies.txt
  
Returns the list of jar files under the fire-lib directory
----------------------------------------------------------

  curl -X POST --header 'Content-Type: application/json' --header 'Accept: text/html' 'http://localhost:8080/libJars' -b /tmp/cookies.txt
  
Returns the Spark Configuration for the username
------------------------------------------------

  curl -X GET --header 'Accept: text/html' 'http://localhost:8080/retrieveSparkConfig/admin' -b /tmp/cookies.txt
  
Delete Workflow Executions by days
----------------------------------
 
"days": "3"::

  curl -X GET --header 'Accept: text/html' --header 'days: 3' 'http://localhost:8080/deleteWorkflowExecutionByDays' -b /tmp/cookies.txt
  
List all the workflow executions by all users
---------------------------------------------
 
  curl -X GET --header 'Accept: text/html' 'http://localhost:8080/executionsByAllUsers' -b /tmp/cookies.txt
  
Get Executed Task Count
-----------------------
 
  curl -X GET --header 'Accept: text/html' 'http://localhost:8080/getExecutedTaskCount' -b /tmp/cookies.txt
  
Get Latest Executions
---------------------
 
  curl -X GET --header 'Accept: text/html' 'http://localhost:8080/getLatestExecutions' -b /tmp/cookies.txt
  
View the latest execution result of workflow
--------------------------------------------
 
"workflowId": "1",

"nodeId": "1"::

  curl -X GET --header 'Accept: text/html' --header 'workflowId: 1' --header 'nodeId: 1' 'http://localhost:8080/recentExecutionResult' -b /tmp/cookies.txt


View  the execution result for specific node
--------------------------------------------
 
"workflowId": "1",

"nodeId": "1"::

  curl -X GET --header 'Accept: text/html' --header 'workflowId: 1' --header 'nodeId: 1' 'http://localhost:8080/viewExecutionResultsForNode' -b /tmp/cookies.txt
   

