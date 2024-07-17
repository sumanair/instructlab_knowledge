watsonx.ai invoke

Use the watsonx.ai invoke policy to invoke watsonx.ai operations.

Gateway support
-   Gateway: DataPower® API Gateway
    Policy version: 1.0.0

This topic describes how to configure the policy in the assembly user interface; for details on how to configure the policy in your OpenAPI source, see watsonx-ai-invoke.

About
The watsonx.ai invoke policy provides access to three watsonx.ai operations:
POST /text_generation
POST /text_tokenization
GET /foundation_model_specs
The watsonx.ai invoke policy supports the properties shown in Table 2.

Properties
The following table lists the policy properties, indicates whether a property is required, specifies the valid and default values for input, and specifies the data type of the values.

watsonx.ai invoke policy properties
- Title: 
    Required: No
    Description: The title of the policy; the default value is watsonx-ai-invoke text generation.
    Data type: string
- Description: 
    Required: No
    Description: A description of the policy.
    Data type: string
- watsonx.ai Operation: 
    Required: Yes
    Description: The watsonx.ai operation to invoke; must be one of the following operations:
        POST text_generation
        An HTTP POST operation for /text_generation. See Infer text in the watsonx.ai documentation for sample request and response examples.

        POST text_tokenization
        An HTTP POST operation for /text_tokenization. See Text tokenization in the watsonx.ai documentation for sample request and response examples.

        GET foundation_model_specs
        An HTTP GET operation for /foundation_model_specs. See List the available foundation models in the watsonx.ai documentation for sample response examples.

        If the request payload contains a project_id property, it is ignored and the policy's own project_id property is used.
    Data type: string
- watsonx.ai Operation Version: 
    Required: Yes
    Description: The watsonx.ai API operation version, using the format yyyy-mm-dd.To see the available version dates, refer to Active Version Dates in the watsonx.ai API documentation. For information on API versioning in watsonx.ai, see Versioning in the same documentation.
    Data type: string
- watsonx.ai Project Id: 
    Required: Yes
    Description: The ID of the watsonx.ai project used for resolving API requests.
    Data type: string
- watsonx.ai Region
    Required: Yes
    Description: The IBM Cloud region where watsonx.ai requests are sent.
    Data type: string
- Response Cache Expiration
    Required: No
    Description: The duration of the cache (the time-to-live). The minimum duration is 60 seconds and the maximum duration is 86400 seconds (1 day) -- any value outside of that range will fail validation when the API is published, even if the value is accepted in this field.
    Data type: integer
- Cache Scope
    Required: No
    Description: A string that adds uniqueness to the key used to store a cached response. Adding a cache scope enables the same request to be saved in multiple cache entries.
    Data type: string
- Enable response caching
    Required: Yes
    Description: Response caching is enabled by default to optimize API performance; however, you can disable it if needed for your API.
    When response caching is enabled, then when a request is sent to the watsonx.ai service, the response cache is inspected to determine if the request payload has an associated cached response. If so, that cached response and its associated HTTP response headers are placed into the DataPower API Gateway context message specified by the Output Message property.

    If there is no cached response, the request is passed to the watsonx.ai service, and the response is cached for subsequent operations using the time-to-live specified in the Response Cache Expiration property.
    Data type: boolean
- Output Message
    Required: No
    Description: The name of the DataPower API Gateway context message that receives the watsonx.ai response. By default, this property uses message as the value, which enables the response to be accessible by future API policies in message.body and message.headers.
    Data type: string
