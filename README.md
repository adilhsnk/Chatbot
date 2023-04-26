# Import necessary libraries
import random

# Define a list of possible responses
responses = {
    "hi": ["Hello!", "Hi there!", "Hey!"],
    "how are you": ["I'm doing well, thank you for asking.", "I'm great, thanks for asking!"],
    "what's your name": ["My name is Chatbot.", "You can call me Chatbot!"],
    "what is your name": ["My name is Chatbot.", "You can call me Chatbot!"],
    "who are you": ["My name is Chatbot.", "You can call me Chatbot!"],
    "bye": ["Goodbye!", "See you later!", "Bye!"]
}

# Define a function to process the user's input
def process_input(input_text):
    # Convert input text to lowercase
    input_text = input_text.lower()

    # Check if the input text matches any of the response keys
    for key in responses:
        if key in input_text:
            # If a match is found, return a random response from the list of responses
            return random.choice(responses[key])

    # If no match is found, return a default response
    return "I'm sorry, I didn't understand what you said."

# Define a function to start the chatbot
def start_chat():
    print("Hello, I am Chatbot. How can I help you today?")

    # Start an infinite loop to continuously process the user's input
    while True:
        # Get the user's input
        user_input = input("User: ")

        # If the user enters "bye", break out of the loop and end the chat
        if user_input.lower() == "bye":
            print("Chatbot: Goodbye!")
            break

        # Process the user's input and print the chatbot's response
        response = process_input(user_input)
        print("Chatbot: " + response)

# Call the start_chat() function to begin the chatbot
start_chat()
