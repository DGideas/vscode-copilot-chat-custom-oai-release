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

## Package your own VSIX
Instead of using our release package, you can package your own VSIX file by doing the following:
1. Clone the [VSCode Copilot Chat repo](https://github.com/microsoft/vscode-copilot-chat) to your local machine.
2. Update extension version and VSCode version requirements in `package.json` and `package-lock.json`.
3. In `package.json`, find the `customoai` vendor entry in `languageModelChatProviders` (around line 1728) and remove the `when` condition:
   ```json
   {
       "vendor": "customoai",
       "when": "productQualityType != 'stable'",  // ← Remove this line
       "displayName": "OpenAI Compatible",
       "managementCommand": "github.copilot.chat.manageBYOK"
   }
   ```
4. Run `npm install`.
5. In `package.json`, replace the `		"package": "vsce package",` line with `		"package": "vsce package --allow-package-all-secrets",`.
6. Run `npm run compile && npm run package`.
