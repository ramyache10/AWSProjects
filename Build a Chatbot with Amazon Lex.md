<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Chatbot with Amazon Lex

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-ai-lex1)

**Author:** Ramya Reddy  
**Email:** ramyareddy5018@gmail.com

---

## Build a Chatbot with Amazon Lex

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex1_505be5b8)

---

## Introducing Today's Project!

### What is Amazon Lex?

Amazon Lex is a service that lets you build chatbots using voice and text. It uses natural language understanding to help bots recognize user input and respond intelligently, making conversations more interactive and efficient.

### How I used Amazon Lex in this project

Services I used were Amazon Lex and AWS IAM. Key concepts I learned include intents, utterances, slots, fallback handling, and how to build conversational chatbots that respond to voice or text using natural language understanding.

### One thing I didn't expect was...

One thing I didn't expect in this project was how easily Amazon Lex could handle natural language inputs and automatically manage conversation flow, making chatbot creation faster and more intuitive than I anticipated.

### This project took me...

This project took me approximately 1 hour to complete. The most challenging part was configuring fallback responses effectively. It was most rewarding to see the chatbot understand user greetings and respond naturally through voice or text.

---

## Setting up a Lex chatbot

I created my chatbot from scratch with Amazon Lex. Setting it up took me around 15–20 minutes, including defining intents, utterances, responses, and configuring basic settings for voice and text interaction.

While creating my chatbot, I also created a role with basic permissions because it allows Amazon Lex to access essential AWS services securely, such as Amazon polly which helps in converting text into speech

In terms of the intent classification confidence score, I kept the default value of 0.40. This means Lex will match an intent only if it’s at least 40% confident, reducing misinterpretations and improving chatbot accuracy.

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex1_97dc2351)

---

## Intents

Intents are goals or purposes behind a user’s input in a chatbot conversation. They represent what the user wants to do—like checking a balance or transferring money—and trigger the appropriate response or action from the bot.

I created my first intent, WelcomeIntent, to greet users when they start a conversation with BankerBot. It helps set a friendly tone and guides users by providing an initial response and suggestions for what they can ask or do next.

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex1_505be5b8)

---

## FallbackIntent

I launched and tested my chatbot, which could respond successfully if I enter greetings like "hi," "hello," "I need help," or "can you help me?"—triggering the WelcomeIntent and providing a friendly welcome message.

My chatbot returned the error message 'Intent FallbackIntent is fulfilled' when I entered a phrase it didn’t recognize, like "How are you?." This error message occurred because the input didn’t match any defined intents, triggering the

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex1_505be5b8)

---

## Configuring FallbackIntent

FallbackIntent is a default intent in every chatbot that gets triggered when the user's input doesn't match any of the defined intents with sufficient confidence, helping handle unexpected or unclear messages gracefully.










I wanted to configure FallbackIntent because it helps the chatbot handle unrecognized input gracefully, offering helpful responses and keeping the conversation on track instead of ending abruptly or confusing the user.

---

## Variations

To configure FallbackIntent, I added polite, user-friendly messages like “Sorry, I didn’t get that. Can you please rephrase?” and enabled it to handle unrecognized inputs, ensuring smoother conversations and better guidance for users.

I also added variations! What this means for an end user is that the chatbot can understand and respond to different ways of saying the same thing, making conversations feel more natural and improving the bot’s ability to recognize user intents.

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex1_c4fc89af)

---

## Initial Responses

As an extension for this project, I'm setting up initial responses, which are crafted to be engaging, varied, and user-friendly. These responses help the chatbot handle confusion or unexpected inputs gracefully. I've set up initial responses for the FallbackIntent, so when the chatbot doesn't understand the user's message, it replies with a helpful and friendly message rather than staying silent or sounding robotic. This makes the conversation feel more natural and improves overall user experience, keeping users engaged even during errors.

The initial response messages I set up are a series of friendly and varied replies like “Hmmm this is interesting...” "One moment...” and “Hmm, I’m not sure what you mean”. These are configured under the FallbackIntent in the chatbot's interaction model. For the user, this means the bot feels more responsive and human-like, even when it doesn’t understand a query. It keeps the conversation flowing and encourages the user to try again instead of ending the interaction abruptly.










![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex1_09bcb9701)

---

---
