<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Save User Info with a Lex Chatbot

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-ai-lex4)

**Author:** Ramya Reddy  
**Email:** ramyareddy5018@gmail.com

---

## Save User Info with a Lex Chatbot

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex4_505be5b8)

---

## Introducing Today's Project!

### What is Amazon Lex?

Amazon Lex is a service by AWS that enables developers to build conversational interfaces using voice and text. It uses the same deep learning technologies that power Amazon Alexa, including automatic speech recognition (ASR) and natural language understanding (NLU).

It is useful because it allows you to create intelligent chatbots that can understand user input, respond naturally, and integrate with backend systems through AWS Lambda. Lex supports multi-turn conversations, slot filling, context management, and real-time fulfillment, making it ideal for building virtual assistants, customer service bots, and automation tools that deliver personalized and interactive user experiences.

### How I used Amazon Lex in this project

In today’s project, I used Amazon Lex to build a conversational chatbot called BankerBot. I used Lex to create and manage multiple intents like CheckBalance and FollowupCheckBalance, set up slot types to capture user inputs (e.g., account type and date of birth), and applied context tags to carry information across the conversation. Lex helped me design a natural, multi-turn dialogue where the bot remembers user details and responds intelligently without repeating questions.

### One thing I didn't expect in this project was...

One thing I didn’t expect in this project was how powerful and seamless context tags could be in managing multi-turn conversations. I was surprised at how easily they allowed the chatbot to remember user information across intents, making the interaction feel much more natural—almost like talking to a real person. It really highlighted how thoughtful design in Lex can create smarter, more human-like bots

### This project took me...

This project took me 1 hour to complete. During that time, I:
Set up the BankerBot chatbot in Amazon Lex.
Created the main intents: WelcomeIntent, CheckBalance, and FallbackIntent.
Designed the CheckBalance intent to collect user information like account type and date of birth.
Added an output context tag to CheckBalance and configured a new FollowupCheckBalance intent with an input context to manage follow-up questions.
Used session attributes to carry over the user's birthday without asking again.
Integrated a Lambda function to return random balance amounts.
Overall, I learned how to manage user memory in a conversation and improve the chatbot's flow using Lex features like slots, contexts, and session management all within an hour.

---

## Context Tags

Context tags are markers used in chatbot platforms like Amazon Lex to manage the flow of conversation by controlling when certain intents are active or can be triggered. They help create more intelligent and contextual interactions by enabling or disabling intents based on what the user has previously said or done.

For example, when a user initiates a conversation to check their balance, a context tag like CheckingBalance can be set. This tag can then be used to allow follow-up intents (like confirming account type or saving user preferences) to trigger only when that tag is active. Once the task is complete, the tag can be cleared to reset the context.

Context tags are particularly useful in multi-turn conversations, where the chatbot needs to remember what the user was doing a few steps ago and respond accordingly. They help manage intent transitions and ensure the chatbot stays relevant and coherent, especially in scenarios involving slot-filling, confirmations, and responses.

There are two types of context tags: input and output context tags.
Output context tags are set by an intent after it's fulfilled and signal what the chatbot should remember going forward.
Input context tags control when an intent can be triggered—they activate only if the required context is already set. Together, they help manage conversational flow by tracking what the user is doing and enabling appropriate follow-up actions.

I created a context tag called contextCheckBalance. This context tag was created in the CheckBalance intent. This tag stores information about the user’s current interaction related to checking their account balance. It helps the chatbot remember that the user is in the middle of a balance inquiry, allowing follow-up intents (like confirming account type or using previously captured information) to activate only when this context is active, ensuring a smooth and relevant conversation.

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex4_97dc2351)

---

## FollowUpCheckBalance

I created a new intent called FollowupCheckBalance. The purpose of this intent is to handle follow-up questions from the user after they’ve already checked one account’s balance, such as “What about my savings account?” This intent uses previously saved information, like the user’s birthday, and only asks for the new account type. It ensures a smooth and contextual conversation without repeating questions the bot already knows the answers to

This intent is connected to the previous intent I made, CheckBalance, because it relies on the context and information captured during that interaction—specifically the user's dateOfBirth. By using an input context tag (e.g., contextCheckBalance), FollowupCheckBalance is only triggered after CheckBalance has been used. This ensures a smooth, continuous conversation where the chatbot remembers the user’s details and only asks for new information, like a different account type.



![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex4_12345678)

---

## Input Context Tag

I created an input context, contextCheckBalance, that connects to the output context of the CheckBalance intent. When the CheckBalance intent is successfully fulfilled, it sets the output context as contextCheckBalance. This context remains active for a specified duration or number of turns, allowing follow-up intents—like FollowupCheckBalance—to be triggered only when this context is present. This connection ensures the chatbot understands that the user is still within the scope of a balance inquiry and enables a seamless transition between related intents without repeating questions.



![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex4_c4fc89af)

---

## The final result!

To see the context tags and followup intent in action, I first asked the chatbot something like “What’s my checking account balance?” to trigger the CheckBalance intent. After receiving the response, I followed up with a phrase like “What about my savings account?” or “Can you check my other account?” This triggered the FollowupCheckBalance intent, which used the saved birthday from the previous intent and only asked for the new account type—showing how context tags enable smooth, natural conversation flow.

If I had gone straight to trying to trigger FollowupCheckBalance without setting up any context, the chatbot wouldn’t have the required information—like the user’s dateOfBirth—and the intent would likely fail or prompt for missing slots. Since FollowupCheckBalance is designed to work only when the context (like contextCheckBalance) is active, triggering it without first going through CheckBalance would break the conversational flow and result in confusion or incomplete responses.

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex4_505be5b8)

---

## Managing context expiry

---

---
