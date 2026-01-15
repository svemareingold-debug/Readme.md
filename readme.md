# Command Line Interfaces (CLIs)
In this documentation, I will go over the configuration of Aider and Cline. Aider is a terminal-based AI coding assistant that works alongside your IDE, so it will work for both VSCode and for Intellij. Cline is a VSCode extension, so it will not be available for Intellij.

<span style="color: red;">THESE ARE NOT MULTIMODEL TOOLS:</span> In order to change the model you are using, you will have to manually update the configuration
## Table of Contents
- [Aider](#aider)
- [Cline](#cline)



# Aider
Aider is a terminal-based AI coding assistant that excels at autonomous, project-wide operations. It reads and edits multiple files simultaneously, making coordinated changes across your entire codebase. Every modification is automatically committed to Git with descriptive messages, creating a clean, reviewable history. Unlike Continue.dev, Aider can execute shell commands—installing dependencies, running tests, and managing your development workflow directly. Where Continue focuses on single-file assistance, Aider shines at large-scale refactoring, ensuring consistency and coordination across your entire project.

### Installation
```
python3 -m pip install aider-chat
```
Or if that doesn't work:

```
pip3 install aider-chat
```
### Configuration
Open your ~/.aider.conf.yml file (you might have to create it) and add this:

```
openai-api-base: https://litellm.reingold.com
openai-api-key: XXXXXXXXXXXXX
model: openai/MODEL-NAME
show-model-warnings: false
auto-commits: true
dirty-commits: true
edit-format: diff
```
Note: For some reason, some of the models don't work unless you add the provider in the beginning (openai). In case you run into any connection issues.

edit-format: diff ensures that aider only returns the changed portions of the code rather than the entire file, even the unchanged portions. It'll help keep your token usage low.

This CLI does not have a multimodel format, so to use different models you would have to go back to the config file and change the model.

### Run

To run, go to your project directory in the terminal and run ```aider``` 

This will start a chat with aider with no files added. Aider needs files added to the chat in order to read and edit them. It will prompt you to add files in the chat and you just have to press Y. 
Alternatively, you can also start the chat by running ```aider <filename1> <filename2> etc.``` to add whatever files you would like automatically. The chat will look like this:

<img width="1847" height="671" alt="E8A51743-64F7-41D0-B229-4378AE813EF5" src="https://github.com/user-attachments/assets/bf4b1ddc-3aee-4751-a977-04001e5024cb" />


# Cline

<img width="548" height="729" alt="72E9302B-7D9A-49E3-A3C6-8A4788AB9F14" src="https://github.com/user-attachments/assets/af4ba5ca-0b5a-46ed-b911-60b78c6b9f4b" />

