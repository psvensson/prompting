# Prompting

A collection of instruction ot be sent to LLM AIs for different purposes.

## Overview

These files are currently geared towards being used with AutoGPT (https://github.com/Significant-Gravitas/Auto-GPT) and so starts out with a file called ai_settings.yaml.
That filed contains some basic instructions and was limited to five specific ones for historic reasons.

One promising venue to get better results from the AI has been to refer to other files accessible to AutoGPT in the local filesystem and to break out generic instructions from specific ones.
For example, for the coding prompts, the main file is called instructions.txt and define limits and base rules for how to code, and it then refer to another file program.txt which contain the spcific instructions for the program to be coded.

## Technicalities

It is easy to ask for too much and better results is found with very clear and limited instructions. So again in the coding example, the instructions explicitly avoids testing or execution of external programs, just the generation of code.
This might not be a smart move. it might be better to start with testing, who knows. Please test and try out what works better for you.

One important factor which is often overlooked is to modify the temperature setting of the AI when trying to get good results back. Temperatue is a bit like creativity or randomness. I get the ffeling that lower tmperatures (like 0.4 (from the standard 1.0)) with very clear instruction give better results.

## How to use

Finally, these files can of course just be pasted together (modifying the references to external files then obviously) and sent to any old LLM, local or external. There is nothing specific about AutoGPT except for the ai_settings format. But that is genric enought to be parsed by any modern AI.
