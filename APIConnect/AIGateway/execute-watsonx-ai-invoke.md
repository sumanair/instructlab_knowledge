watsonx-ai-invoke
Use the watsonx.ai invoke policy to invoke watsonx.ai operations.

Gateway Support
The DataPower API Gateway supports the watsonx.ai invoke policy with version 1.0.0.

Ahis topic describes how to configure the policy in your OpenAPI source; for details on how to configure the policy in the assembly user interface, see watsonx.ai invoke.

About
The watsonx.ai invoke policy provides access to three watsonx.ai operations:
POST /text_generation
POST /text_tokenization
GET /foundation_model_specs

Properties
- Version:
    Required: Yes
    Description: The policy version number. It must be compatible with the gateway being used.
    Data type: string
- Title:
    Required: No
    Description: The title of the policy; default value is watsonx-ai-invoke text generation.
    Data type: string
-Description:
    Required: No
    Description: A description of the policy.
    Data type: string
- Operation:
    Required: Yes
    Description: The watsonx.ai operation to invoke. Must be one of POST /text_generation, POST /text_tokenization, or GET /foundation_model_specs.
    Data type: string
- Op-version:
    Required: Yes
    Description: The watsonx.ai API operation version, using the format yyyy-mm-dd.
    Data type: string
- Project ID:
    Required: Yes
    Description: The ID of the watsonx.ai project used for resolving API requests.
    Data type: string
- Region:
    Required: Yes
    Description: The IBM Cloud region where watsonx.ai requests are sent.
    Data type: string
- Cache TTL:
    Required: No
    Description: The duration of the cache (time-to-live). Must be between 60 and 86400 seconds.
    Data type: integer
- Cache Scope:
    Required: No
    Description: Adds uniqueness to the key used to store a cached response.
    Data type: string
- Enable Cache:
    Required: Yes
    Description: Enables or disables response caching. Default is enabled.
    Data type: boolean
- Output:
    Required: No
    Description: The name of the DataPower API Gateway context message that receives the watsonx.ai response. Default is message.
    Data type: string

Example
- watsonx-ai-invoke:
    version: 2.0.0
    title: watsonx-ai-invoke text generation
    description: get an AI response to the provided prompt
    region: us-south
    operation: POST text_generation
    op-version: '2024-03-14'
    enable_cache: true
    cache_ttl: 60
    project_id: $(watsonx-ai-projectid)
    output: watsonxaiResponse
    cache_scope: somesaltkey
