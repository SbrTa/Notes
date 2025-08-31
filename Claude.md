# Claude

### Command
- ```npm install -g @anthropic-ai/claude-code```
- run ```claude``` at your terminal. The first time you run this command you will be prompted to authenticate
- Start with ```/init```, it helps claude analyzes the codebase for context
- ```# anything``` - # refers to memory mode. Can be useful to teach claude some practices it should follow.
- ```@file``` - when asking question, you can tag related file for better direction.
- ```shift``` + ```tab``` - plan mode
- ```esc``` + ```esc``` - conversation history
- ```\compact``` - clears conversation history, but keep a summary in context
- ```\clear``` - clears conversation history and free up context
- Custom command: you can create your own custom command and use it when required.
  - project_path/.claude/commands/audit.md
    ```
    //audt.md
    The goal is to update any vulnerable dependency.
    Do the followings:
    1. Run npm audit to find vulnerable installed packages
    2. Runs npm audit fix to apply updates
    3. Runs tests to verify the updates didn't break anything

    // now use /audit in claude
    ```
    
- sdsdf
