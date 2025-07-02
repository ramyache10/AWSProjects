

# Set Up Multiple Slots in a Lex Chatbot


**Author:** Ramyasri Chapala 
**Email:** ramyareddy5018@gmail.com

---

## Build a Chatbot with Multiple Slots

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex5_67890123)

---

## Introducing Today's Project!

### What is Amazon Lex?

Amazon Lex is a fully managed service by AWS for building conversational interfaces using voice and text. It uses the same natural language understanding (NLU) and automatic speech recognition (ASR) technology that powers Amazon Alexa.

It is useful because it allows developers to easily build chatbots and virtual assistants that can understand user input, carry on multi-turn conversations, integrate with backend systems (like Lambda), and provide personalized, real-time responses. Lex simplifies complex language processing tasks, making it ideal for automating customer support, self-service tools, and intelligent assistants across various platforms.

### How I used Amazon Lex in this project

In today's project, I used Amazon Lex to build a chatbot called BankerBot that can interact with users through natural language. I created multiple intents like CheckBalance, FollowupCheckBalance, and TransferFunds, and used slots to collect information such as account type and date of birth. I also integrated AWS Lambda to generate dynamic responses and used context tags to manage multi-turn conversations. Lex made it easy to design, test, and deploy an intelligent and responsive banking assistant.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was how everything—like intents, slots, and responses—was automatically created and configured after deploying the CloudFormation template. It was surprising to see how powerful and hands-off the process became once the template was set up correctly. It saved a lot of time and effort compared to manually building each part in the Lex console.

### This project took me...

This project took me around 1 hour to complete. That includes setting up the chatbot manually in Amazon Lex, learning how to automate the process using CloudFormation, troubleshooting permission issues, and successfully deploying a fully functional version of BankerBot with intents, slots, and Lambda integration.

---

## TransferFunds

An intent I created for my chatbot was TransferFunds, which allows users to transfer money from one account to another by collecting key details like the source account, destination account, and transfer amount. This intent uses two accountType slots to identify the accounts involved and helps simulate a real banking scenario. It enhances BankerBot’s functionality by enabling more advanced user interactions beyond simple balance checks.

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex5_67890123)

---

## Using multiple slots

For this intent, I had to use the same slot type twice. This is because I needed to capture two different account types—one for the source account and one for the destination account—but both use the same list of possible values (e.g., checking, savings, credit). By reusing the accountType slot type for both slots, the bot can correctly identify where the money is coming from and where it's going, enabling a proper funds transfer conversation.

I also learnt how to create confirmation prompts, which are messages the chatbot uses to double-check with the user before performing an action. For example, before transferring money, the bot might say, "Do you want to transfer $500 from your savings to your checking account?" This gives the user a chance to confirm or cancel the action, helping prevent mistakes and making the conversation more interactive and reliable.

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex5_97dc2351)

---

## Exploring Lex features

Lex also has a special conversation flow feature that visually maps out how the chatbot interacts with the user throughout the conversation. It shows the sequence of prompts, slot collection, confirmation messages, and responses, helping developers easily understand and debug the flow of logic in an intent. This feature makes it easier to design smooth, multi-turn conversations and identify any gaps or misconfigurations in the dialogue structure.



You could also set up your intent using a visual builder! A visual builder provides a drag-and-drop interface that lets you design chatbot conversations without writing code. It helps you define intents, slot prompts, confirmation messages, and responses visually. This makes building and managing complex conversations easier, faster, and more intuitive—especially for beginners or when collaborating with non-technical team members.

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex5_12345678)

---

## AWS CloudFormation

AWS CloudFormation is a service that helps you automate and manage your AWS infrastructure as code. It allows you to define all your cloud resources—like EC2 instances, Lambda functions, S3 buckets, IAM roles, and even Amazon Lex bots—in a template written in JSON or YAML.
This means you can set up, update, and delete complex environments reliably and repeatedly, without needing to manually configure each service. CloudFormation is especially useful for deploying consistent infrastructure across different environments (e.g., dev, test, prod) with minimal effort and maximum control.

I used CloudFormation to automate the setup of my BankerBot chatbot, including all its intents, slot types, and configuration. Instead of manually recreating the bot in the Amazon Lex console every time—going through each page and setting up components one by one—I defined everything in a CloudFormation template.

This allowed me to deploy the entire chatbot in seconds, making the process faster, more consistent, and easier to maintain. It also gave me insight into how real engineering teams use infrastructure-as-code tools like CloudFormation to streamline development and avoid repetitive manual setup.

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex5_c4fc89af)

---

## The final result!

Re-building my bot with CloudFormation took me 1 hour. During that time, I learned how to define all the components—like intents, slots, and responses—in a single template and deploy them automatically. It was much faster and more efficient than manually recreating everything through the Lex console, and it gave me a better understanding of how infrastructure as code can streamline bot development.

There was an error after I deployed my bot! The error was a permission issue between Amazon Lex and the Lambda function. Lex wasn’t able to invoke the function due to missing permissions.
I fixed this by adding an AWS Lambda permission that explicitly allowed Lex to call the function. Once the correct IAM policy was in place, the bot worked as expected. This helped me understand how critical proper permissions are when integrating AWS services.

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex5_505be5b8)

---

## Using the visual builder

Using the visual builder, I added a Get slot value card to capture which account the user wants to check, a Condition card to evaluate the account type, and a Go to intent card to transition to the CheckBalance intent based on the result.

What this means for an end user is that after transferring funds, the chatbot can smoothly ask, understand, and respond to follow-up questions—like checking the updated balance without restarting the conversation, creating a more natural and helpful experience.

The new Get slot value card will trigger when the TransferFunds intent finishes and the conversation reaches the next step. This card will try to capture the accountType the user wants to check the balance for after the transfer. It sets up the next part of the flow by retrieving the user's intent to continue the conversation, making it easier to transition smoothly to CheckBalance without asking repetitive questions.

![Image](http://learn.nextwork.org/daring_cyan_noble_chicken/uploads/aws-ai-lex5_9cac15cd4)

---

---
