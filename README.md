# Alexa Find my Phone
# Title

Alexa Skill to find phone by making phone calls.

## Table of Contents

### To be Modified

- [Security](#security)
- [Background](#background)

## Background

### Introduction
Alexa Find my Phone is a python-based Alexa Skill helping users to find phone by making phone calls. It will use 

## Dialog Command
+ "Alexa, Find my Phone"
	
	​	The command to start the Skill
	
+ "Find my phone"

  ​	Start finding your phone. 

  + If the number is saved in AWS databse:  it will repeat it and, after your confirmation, it call your phone. 
  + If no nubmer saved in AWS database: it will ask for your phone

+ "My phone number is XXX"
	The skill will call your phone and save it in database.


## License

[MIT © Richard McRichface.](../LICENSE)