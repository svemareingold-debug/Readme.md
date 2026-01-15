# Aider


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

This CLI does not have a multimodel format, so to use different models you would have to go back to the config file and change the model.



