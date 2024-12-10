# Basic-Power-Automate-Data-Analysis
This is a walkthrough of how to run a simple data analysis pipeline using Microsoft's Power Automate and AzureGPT:
1) Upload the right file to the corresponding OneDrive folder. The names of these folders follow the same naming conventions as the files.
2) Wait for an email to come from MS Power Automate. Select yes to approve the data analysis if the information appears correct.
3) You should then receive another email containing the data analysis.

Here are the directions to create this type of flow:
1) Choose trigger action "When a file is created" to begin the flow and choose the folder to check for new files. I used OneDrive for Business but you can also use Sharepoint if preferred. You can also adjust the frequency that the flow checks the folder for new uploads. 
2) Call the AI Builder action "Create text with GPT using a prompt." You will have to choose what output the GPT will use with the prompt; use the file content of the previous action.
3) You will also have to create a prompt for the action to use. This is easy, just choose prompt and then "New custom prompt."
4) The next action is "Start and wait for an approval", which begins the process of data analysis. This prompts you to choose the Approval type, choose First to respond and enter the email(s) of who you want to approve the output.
5) Finally add the Outlook action "Send an email (V2)" to email the relevant parties the GPT's response.

Warning! Currently in this project the email being sent is not properly HTML formatted and will return the response in a hard-to-read manner.
