

# Add Custom Slots to a Lex Chatbot



**Author:** Ramyasri Chapala  
**Email:** ramyareddy5018@gmail.com

---

## Add Custom Slots to a Lex Chatbot

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex2_c4fc89af)

---

## Introducing Today's Project!

In today's project, I used Amazon Lex to build BankerBot, a chatbot that can greet users, collect their account type and birthday, and respond with their account balance. I created intents, slots, and utterances to handle user interactions smoothly.

### What is Amazon Lex?

Amazon Lex is a service for building chatbots using voice and text. It is useful because it understands natural language, automates tasks, and enables real-time, intelligent conversations to enhance user experience.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was how easily Amazon Lex could capture and process user inputs like account type and birthday using slots, making it simple to build a functional, personalized chatbot without writing complex backend code.

### This project took me...

This project took me approximately 1.5 hours to complete. Setting up intents and slots was straightforward, but fine-tuning utterances and customizing responses for better user interaction took extra time and was a valuable learning experience.

---

## Slots

Slots are data fields in Amazon Lex that collect specific information from the user, such as account type or birthdate. They help the bot gather the details needed to fulfill an intent and guide the conversation flow effectively.










By adding custom slots in utterances, my chatbot's users can interact more naturally by including details like account type or birthday in their messages. This helps Lex capture key info faster and makes conversation feel smoother and personalized.

In this project, I created a custom slot type to define specific bank account types like checking and savings. This ensures BankerBot accurately understands user input and maps it to valid options needed to retrieve the correct account balance.

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex2_97dc2351)

---

## Connecting slots with intents

This slot type has restricted slot values, which means the bot will only accept user input that matches the defined values, helping improve accuracy and preventing unexpected or invalid responses during the conversation.

I associated my custom slot with CheckBalance, which is the intent that collects the user’s account type and birthday. It uses this information to identify the correct account and return the current balance in response to the user’s request.

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex2_c4fc89af)

---

## Slot values in utterances

I included slot values in some of the utterances (i.e. user inputs) by using curly braces to reference the slots. For example, “What’s my {AccountType} balance?” and “Check my {AccountType} balance from {BirthDate}” allow Lex to capture user details.

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex2_505be5b8)

---

## Handling failures in slot values

I added variations for the dateOfBirth slot prompt, such as: “For verification purposes, what is your date of birth?”, “Sorry, that wasn't clear to me. What's your date of birth?”, and “Hmm, that didn't work either. Try sharing your date of birth as MM/DD/YY.” The messages play in order, so my end user will see increasingly helpful prompts if they don’t respond correctly the first time. This guides them clearly toward providing the correct input format.

I also used failure responses to ensure the chatbot handles errors or unrecognized inputs in a helpful and user-friendly way. These responses guide users when something goes wrong, like a failed intent or invalid input. A default setting I changed was the generic error message—I replaced it with more specific and varied responses that clearly explain the issue and suggest the next step, keeping the conversation smooth and informative.

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex2_a028bc8d2)

---

---
