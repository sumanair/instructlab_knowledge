Cloud Authentication Policy
Use the IBM Cloud Authentication policy to authenticate with IBM Cloud and obtain an API key that can be used when sending requests to watsonx.ai.

Gateway support
- Gateway: DataPower® API Gateway
  Policy version 2.0.0

This topic describes how to configure the policy in the assembly user interface; for details on how to configure the policy in your OpenAPI source, see ibm-cloud-authentication.

About
The IBM Cloud Authentication policy provides an API key to the IBM Access Manager and, if successfully authenticated, returns a Bearer token to be used by all subsequent watsonx.ai operation requests. The Bearer token is cached and will be valid for approximately 60 minutes. A new token is retrieved when a response for the API key was not cached. or expired.

The IBM Cloud Authentication policy supports the properties shown in Table 2.

Properties
- Title: 
    Required: No
    Description: The title of the policy; the default value is ibm-cloud-authentication. The title displays in the API assembly editor in the UI.
    Data type: string
- Description: 
    Required: No
    Description: A description of the policy.
    Data type: string
- API key: 
    Required: Yes
    Description: The API key, or a variable reference to the variable that contains an API key. The API key is used to authenticate subsequent watsonx.ai requests.
    Data type: string 

