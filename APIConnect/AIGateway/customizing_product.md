Customizing the product for an AI Gateway API
Create a product for an AI Gateway API, or customize the product that was generated when you created the API.

If you opted to have the product generated when you created the AI Gateway API, you can edit it to modify its settings, using the example as your model.

If you did not choose to generate a product for the API automatically, create one now as explained in Creating a draft Product. In the product definition, add a plan with the watson-ai-default and watson-ai-infer-text assembly rate limits, as shown in the following example:

plans:
  default-plan:
    title: Default Plan
    description: Default Plan
    approval: false
    rate-limits:
      default:
        value: 100/1hour
    assembly-rate-limits:
      watson-ai-default:
        - value: 200/1minute
          hard-limit: true
          cache-only: false
          is-client: true
          use-api-name: false
          use-app-id: false
          use-client-id: true
          weight: '1'
      watson-ai-infer-text:
        - value: 200/1minute
          hard-limit: true
          cache-only: false
          is-client: true
          use-api-name: false
          use-app-id: false
          use-client-id: true
          weight: aiGeneratedTokenCount

The watsonx.ai assembly rate limits are required
    The product must include a plan with the watson-ai-default and watson-ai-infer-text assembly rate limits, even if you add other plans to the product. You can configure the rate limits as needed for your own requirements.
Token-based rate limiting requires a token count
    The weight: aiGeneratedTokenCount property is required in the watson-ai-infer-text assembly rate limit. This variable indicates the number of tokens that will be added to the counter with each API call, and then compared with the rate limit threshold.
Rate limiting can apply to the catalog or to individual client IDs.
    Rate limiting is configured for the catalog that contains the API. By default, each client ID that subscribes to the plan within a particular catalog is assigned its own rate limit threshold. To configure a single threshold for the entire catalog, set use-client-id: false for that rate limit.