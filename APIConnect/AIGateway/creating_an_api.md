Creating a REST proxy with the AI Gateway
Last Updated: 2024-06-25
Create a REST proxy that uses the AI Gateway to control access to AI models.

Before you begin
Complete the tasks in Prerequisites for using the AI Gateway to ensure that you can authenticate with IBM Cloud and access watsonx.ai.

About this task
The AI Gateway is only supported with OpenAPI 3.0 APIs.

Procedure
In the navigation pane, click Develop icon.
On the Develop page, click Add > API.
On the Select API type page, click the OpenAPI 3.0 tab.
In the Create section, select AI gateway, then click Next.
On the Create API from AI gateway page, provide the properties for the API.
Use the "Info" section to provide basic information about the API, and then click Next:
The OpenAPI version is filled in for you based on the tab that you selected in step 2.
Title: Provide a descriptive title for display in the UI. The title can include special characters but should be kept short.
The Name is filled in for you based on the title. The value is a single string that is used to identify the API in developer toolkit CLI commands.
Version: Accept the default value or modify it as needed. The version corresponds to the value of the info.version property of the OpenAPI definition. The version.release.modification version numbering scheme is recommended; for example 1.0.0.
Base path: Accept the default value or modify it as needed. The API's "base path" is the server URL, which is used to determine the full URL endpoint for the calling the API, taking into account any vanity endpoint configuration in the catalog in which the API is published. For an API that is enforced by the DataPower API Gateway, you only need to provide the base path value. In addition:
Do not include the host name or any additional segments for paths or operations
Do not include special characters
Begin the URL with a forward slash ( / ) even if it is otherwise empty
Description: The optional description helps to identify the API.
Provide information for authenticating with watsonx.ai, and then click Next:
API key: Provide either the API key value, or the name of a catalog property variable whose value is the API key.
The API key allows the API to authenticate with IBM Cloud Authentication, and is required for access to the watsonx.ai service.

Region: Select the IBM Cloud region where watsonx.ai requests are sent.
Operation version: Accept the default value or provide the appropriate Active Version Date of the watsonx.ai API, using the format yyyy-mm-dd.
To see the available version dates, refer to Active Version Dates in the watsonx.ai API documentation. For information on API versioning in watsonx.ai, see Versioning in the same documentation.

Provide information about how the API accesses watsonx.ai to submit requests:
Project ID: Provide either the ID of the watsonx.ai project used for resolving API requests, or a catalog property variable whose value is the ID of the watsonx.ai project.
Exposed paths: Accept the default list of exposed paths, or select only the paths that you want your API to access. The exposed paths define which watsonx.ai operations are included in the generated API.
Enable response caching: Response caching is enabled by default to optimize API performance; however, you can disable it if needed for your API. If you use response caching, you can specify the duration of the cache in the Cache TTL in seconds field.
When response caching is enabled, then when a request is sent to the watsonx.ai service, the response cache is inspected to determine if the request payload has an associated cached response. If so, that response and its associated HTTP response headers are placed into the DataPower API Gateway context message (which by default is named message). The Output Message property in the policy UI can be modified after the API has been generated if a different message is needed.

If there is no cached response, the request is passed to the watsonx.ai service, and the response is cached for subsequent operations using the time-to-live specified in the Cache TTL in seconds property.

Cache TTL in seconds: If you enable response caching, configure the duration of the cache by accepting the default value or selecting (or typing) a new value. The minimum duration is 60 seconds and the maximum duration is 86400 seconds (1 day) -- any value outside of that range will fail validation when the API is published, even if the value is accepted in this field.

In the Rate Limiting section, optionally configure rate limiting, and then click Next:
Select Create product if you want to generate an API Connect product that controls rate limiting for the API.
In API Connect, a product serves as a container for an API and its associated usage plans, which define rate limits. When you enable Create product, a default plan is generated in the product, using your selected rate limits.

If you choose not to generate a product automatically, you must create one as explained in Customizing the product for an AI Gateway API.

Configure the types of rate limiting to enforce on API calls:
Set rate limit : (Time based) Accept the default rate limit or configure a new limit based on the number of API requests sent within a specified period of time. This type of rate limit does not use tokens.
Set AI token limit : (Token based) Accept the default rate limit or configure a new limit based on the number of cost-based tokens used within a specified period of time. Token-based rate limiting uses the /text_generation operation to track token usage.
Review the Summary page to verify that the API has no issues, and then click Done.