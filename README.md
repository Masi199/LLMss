from transformers import pipeline, set_seed
import random

# Set a seed for reproducibility
set_seed(42)

# Load the pre-trained GPT-2 text generation model
generator = pipeline('text-generation', model='gpt2-xl')

# Define the prompt for generating educational content
prompt = "Generate a detailed educational text explaining the process of photosynthesis, including its stages, reactants, products, and importance. The text should be suitable for use in a Virtual Reality or Augmented Reality educational environment:"

# Generate the text
generated_text = generator(prompt, max_length=1000, num_return_sequences=1)[0]['generated_text']

# Print the generated text
print(generated_text)
