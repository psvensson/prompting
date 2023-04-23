# DOLLY - AutoGPT cloning/replication

Dolly showcases how we can teach AutoGPT new commands via prompting alone.

Dolly is a prompt that attempts to teach AutoGPT to popen() another AutoGPT process and farm out work to it. The result is that you get additional clones (agents, replicas) that are not only message agents, but can access all the tools that AutoGPT can access, and can work more independently.

They also work in parallel, speeding up AutoGPT tasks.

## GPT 3.5

GPT 3.5 gets confused by the cloning terminology, so we include a version of dolly that uses "replication" rather than "cloning". Everything else works the same way.

## Files:

- **ai_settings_dolly.yaml:** This is the usual ai_settings file. The main addition is the concept of creating clones (or replicas) instead of sub-agents.
- **auto_gpt_workspace/instructions_dolly.txt:** We add an instruction to read cloning_101.txt, which teaches AutoGPT to clone itself, and to use clone names when creating output files
- **auto_gpt_workspace/ai_settings_clone_template.yaml** This is exactly like ai_settings_dolly.yaml but is templatized. It allows us to have a different settings file for each clone. AutoGPT could generate this file itself, but it was faster to provide a template for it to execute.
- **auto_gpt_workspace/cloning_101.txt** The new skill - setup the right files, and run a popen. => Note that the commands are linux/mac specific (TODO: Make windows commands)


That's it!
- The cloning instructions also set up a separate auto-gpt.json file for each clone.
- Each clone searches the internet, reads and writes files, etc. Because we're using popen, they're working in parallel, asynchronously too.
- No additional software is needed beyond what comes with AutoGPT out of the box (although inter-agent communication may be improved with something else - this is a work in progress.)

## Running it:

Command to start everything:

```
./run.sh --ai-settings ai_settings_dolly.yaml
```

To run the main process in continous mode: 

```
./run.sh --continuous --ai-settings ai_settings_dolly.yaml --continuous-limit 15
```

OR

```
- ./run.sh -c -C ai_settings_dolly.yaml -l 15
```

## Check out the plugin

A plugin version of Dolly is in development at https://github.com/KayLuke/Auto-GPT-Dolly-Plugin

Feedback welcome!