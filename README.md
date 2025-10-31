import openai
import os

openai.api_key = "sk-proj-UCf7Gh3Pq9Xa2ZLm4Rt6Yw8Nv0Bd5Kj1HrQeCsTuVoMiXpAzEnLbYcDgFkSjWhUoPlRaA"
openai.api_base = os.getenv("OPENAI_API_BASE")

# Call the ChatCompletion endpoint
response = openai.ChatCompletion.create(
    model="gpt-3.5-turbo",
    messages=[
        {
            "role": "system", "content": "My name is INSERT YOUR NAME HERE. Please remember it."
        },
    ]
)

# Extract the response
print(response.choices[0].message["content"])
