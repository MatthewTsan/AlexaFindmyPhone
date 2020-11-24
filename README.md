# Alexa Find my Phone

 [![](https://img.shields.io/badge/Language-Python-brightgreen.svg?style=flat-square)](https://github.com/MatthewTsan/Android-Game-Whac-A-Mole/tree/main/WhacAMole) 

 [![](https://img.shields.io/badge/Backend-AWS-white.svg?style=flat-square)](https://github.com/MatthewTsan/Android-Game-Whac-A-Mole/tree/main/WhacAMole)   [![](https://img.shields.io/badge/API-Twilio-red.svg?style=flat-square)](https://github.com/MatthewTsan/Android-Game-Whac-A-Mole/tree/main/WhacAMole) 

# Title

Alexa Skill to find phone by making phone calls.

## Table of Contents

- [Security](#security)
- [Background](#background)
  - [Introduction](#introduction)
- [Dialog Command](#dialog-command)
- [Install and Test](#install-and-test)
  - [Create a Skill on Amazon Alexa Developer](#create-a-skill-on-amazon-alexa-developer)
  - [Create a twilio service](#create-a-twilio-service)
  - [Deploy and test the Skill](#deploy-and-test-the-skill)

## Background

### Introduction
Alexa Find my Phone is a python-based Alexa Skill helping users to find phone by making phone calls. You can:
+ Ask the Skill to help find your phone
+ Tell Skill your phone number and it will rember it
+ Using [Twilio](https://www.twilio.com) Kit, the Skill can make Cloud Phone Calls.

## Dialog Command
+ "Alexa, Find my Phone"
	​	The command to start the Skill
+ "Dial my phone"
	​	Start finding your phone. 
  + If the number is saved in AWS databse:  it will repeat it and, after your confirmation, it call your phone. 
  + If no nubmer saved in AWS database: it will ask for your phone
+ "My phone number is XXX"
	The skill will call your phone and save it in database.
	
## Install and Test

### Create a Skill on Amazon Alexa Developer

This module depends upon Amazon Alexa Development platform. 

1. You will need a Amazon Developer accound. 
	To sign up, please visit the website [Amazon Developer](https://developer.amazon.com)
	
2. Log in

   To get started, log into the [Alexa developer console](https://developer.amazon.com/alexa/console/ask) with your Amazon Developer account. 
   
3. Create your skill
	Fellow the Tutorial Step2 in [Building Alexa Skills](https://developer.amazon.com/en-US/alexa/alexa-skills-kit/get-deeper/tutorials-code-samples/build-an-engaging-alexa-skill/module-3) . Select Python-hosted AWS backend on Step2.e.
	
4. Open Find my Phone skill in the Alexa developer console.

5. Click Build tab -> Interation Model on left sidebar -> Intents. 

6. Click Add Intent Button and add "DialIntent" intent. Add Sample Utterances "dial my phone" and save the model. 

7. Add another Intent "SavePhoneNumberIntent". Add Sample Utterances "my phone number is {phone_num}", where click add that create a slot "{phone_num}". At the botton, select slot type "AMAZON.PhoneNumber". Don't forget to save the model.

8. Click the Code tab. The code editor opens the lambda_function.py file. Copy line 19 of  import twilio client module at the begining. 

9. Modified LaunchRequestHandler() and Copy new functions into lambda_functions.py.

10. At the end of file, add those functions into console(line 216-217) so that the skill could the skill could handle those functions. 

11. Open requirements.txt and add other package requirements(line 4 - 11). 

12. Click Save button. 

### Create a twilio service

The skill will require the service of Twilio to make cloud phone calls. Thus, you will need to create a Twilio accound and fellow instructions below:

1. Fellow the Tutorial to [sign up for Twilio and get a phone number](https://www.twilio.com/docs/voice/quickstart/python#sign-up-for-twilio-and-get-a-phone-number)
2. Fellow the Tutorial to [make an outgoing phone call with Python](https://www.twilio.com/docs/voice/quickstart/python#make-an-outgoing-phone-call-with-python). You can find the code in console Code -> lambda_function.py -> line 79 - line 90. Replace all the target information in console.

### Deploy and test the Skill

1. Click Deploy button. It may take a while for console to deploy the skill.
2. Click Test tab. 
3. Test as below:
   1. "Find my phone": start the Skill. 
   2. "Dial my phone": dial the phone
   3. "My phone number is XX": the skill will make a phone call to your phone


## License

[MIT © Richard McRichface.](../LICENSE)
