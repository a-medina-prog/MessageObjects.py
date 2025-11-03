import openai
import os

# The openai.api_key and openai.api_base will now be loaded 
# automatically if the environment variables are set correctly.

# Ensure you have set the OPENAI_API_KEY environment variable.
# Ensure you have set the OPENAI_API_BASE environment variable if using a 
# custom base URL, otherwise, the default OpenAI base URL is used.

# Call the ChatCompletion endpoint
response = openai.ChatCompletion.create(
    model="gpt-3.5-turbo",
    messages=[
        {
            "role": "system", 
            "content": "You are a helpful teacher."
        },
        {
            "role": "user", 
            "content": "My name is Professor Quigley."
        },
        {
            "role": "assistant", 
            "content": "Hello Professor Quigley. How can I help?"
        },
        {
            "role": "user", 
            "content": "What is my name?"
        }
    ]
)

# Extract the response
print(response.choices[0].message["content"])
