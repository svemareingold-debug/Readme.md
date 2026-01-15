# Command Line Interfaces (CLIs)
In this documentation, I will go over the configuration of Aider and Cline. Aider is a terminal-based AI coding assistant that works alongside your IDE, so it will work for both VSCode and for Intellij. Cline is a VSCode extension, so it will not be available for Intellij.

THESE ARE NOT MULTIMODEL TOOLS. In order to change the model you are using, you will have to manually update the configuration

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

### Installation

Go to the extensions in VSCode and search for Cline. You will find this extension:

<img width="1616" height="792" alt="A6F8F0E7-D527-41B8-BF87-AC931EA82D03" src="https://github.com/user-attachments/assets/7a593cc7-8736-444e-9565-0117285dca3d" />

Install it and the Cline icon will appear on your sidebar. Click on the icon and it will take you to the chat bar. On the top right of the chat click on the settings icon and it will take you to the configuration.

### Configuration
The API Provider will have a drop down menu of providers. Choose OpenAI Compatible and set https://litellm.reingold.com as the base url. Your OpenAI Compatible API Key will be your LiteLLM API key. You can add any of the available model ids on LiteLLM as the Model ID in the configuration. <br>
Note: Cline uses complex prompts and works best with Claude models. Less capable models may not work as expected.
<br>

<img width="548" height="729" alt="72E9302B-7D9A-49E3-A3C6-8A4788AB9F14" src="https://github.com/user-attachments/assets/af4ba5ca-0b5a-46ed-b911-60b78c6b9f4b" />

Cline has two modes: plan and act. Plan mode is slower because it thinks of a plan and performs edits after you confirm the plan. This is better for more complex tasks. Act mode is much faster and immediately performs edits on your files. This is better for small and simple tasks. <br>
However, the cool thing about Cline is that you can combine these two modes. If you look at the bottom of the screenshot above, you can see a button that says "Use different models for Plan and Act". Clicking on that would allow you to set up separate configurations for each mode, so you can  use a higher reasoning model to create a complex plan and another model to execute the steps in Act mode. <br>

In Act mode, you can change your settings in the chat to auto approve so that the model can read and edit all files. This makes the agent fully autonomous in coding multiple files. <br>
<img width="382" height="488" alt="CF9E66CF-03F6-480D-89C3-CA2B075AB787" src="https://github.com/user-attachments/assets/338218c8-0ba5-4c89-9752-f83b8d36e911" />

In the image below, Cline is coding two files (flappy_bird.py and styles.css) at the same time <br>
<img width="1620" height="1137" alt="02B594A1-26B5-45BB-8C0B-BDB9C593AD19" src="https://github.com/user-attachments/assets/f6012e94-212a-4687-a4d8-65471a5b86b7" />

