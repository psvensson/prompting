# Sample node.js code generation using AutoGPT

The idea here is to use two steps (more could be made) where the first step is to create instructions and the other is to generate code.
If the process fails at the last step, at least instructions has been made and it can be restarted.
Also, this way we skip a number of slow API calls to OpenAI if we're already done with parts or all of the steps.
