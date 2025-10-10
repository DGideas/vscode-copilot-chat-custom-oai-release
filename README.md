# VSCode Copilot Chat release for Custom OpenAI compatible model support
## What is this repo for?
[VSCode Copilot Chat](https://github.com/microsoft/vscode-copilot-chat) extension is a companion extension that provides conversational AI assistance. It provides the Chat UI experience in Visual Studio Code. From VSCode version 1.104, Copilot chat starts supporting custom OpenAI compatible model, but can only be used in VSCode Insider version. From the [developer's message](https://github.com/microsoft/vscode-copilot-release/issues/7518#issuecomment-3386387767), this support will be held to insiders for the forseeable future. Since some developers need this custom OpenAI model support, this repo will periodically release the VSCode Copilot Chat VSIX extension package which adds the custom OAI model support.

## Releases
See the [releases page](https://github.com/DGideas/vscode-copilot-chat-custom-oai-release/releases).

## How to install
Do note that if you're using SSH remote development, you need to install the copilot extension both on your local machine and your (each) remote server.

1. Open VSCode, and connect to remote SSH if needed
2. Switch to the "extension" page
3. Click the "Views and more actions..."(`...`) button at the top
4. Select "Install from VSIX..."
5. Done!
