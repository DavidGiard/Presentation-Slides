# Azure OpenAI Studio Demo

- Create an Azure OpenAI service [link](./Creating-OpenAI-Service-Demo.md)
- Azure Open AI Studio
    - From Azure OpenAI service "Overview" blade, click [Go to Azure OpenAI Studio]
    - or Navigate to (https://oai.azure.com/)
    - "Model catalog"
        - Explain different models (chat, text to image, smaller LLMs, speech, embeddings, etc.)
        - Select [gpt-4]
        - [Deploy] (very fast)
        - [Open in playground] or [Chat] and select the deployment
            - Point out context
            - Point out [Add section]
                - Safety system messages
                    - Harmful content
                    - Avoid ungrounded content (reduces hallucinations by pointing to specific source)
                    - Copyright infringements
                    - Jailbreak (manipulating AI with prompts that circumvent its guardrails)
                - Examples
                    - add prompts and responses
            - Enter prompts
                - What is  the capital of Oklahoma?
                - Write an outline for a 10-slide presentation on Azure OpenAI.
                - Expand on slide 3. Write 3 paragraphs about this.