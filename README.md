PromptsApp
A simple Node.js library that repeatedly prompts the user for input until a specific command is entered.
Installation

Ensure you have Node.js installed.
Save the promptsapp.js file in your project directory.
Install dependencies (none required for this library as it uses the built-in readline module).

Usage
The PromptsApp class allows you to prompt the user for input until they enter a specified target command. Here's an example of how to use it:
Example
const PromptsApp = require('./promptsapp');

async function main() {
    // Create an instance with the target command "exit"
    const app = new PromptsApp('exit');
    
    // Start prompting with a custom message
    await app.start('app> ');
    
    console.log('Target command received, application stopped.');
}

main();

In this example:

The user is prompted with app>  until they type exit.
Once exit is entered, the prompt stops, and the program continues.

API
new PromptsApp(targetCommand)
Creates a new instance of the PromptsApp class.

targetCommand (string): The command that, when entered, stops the prompting.

start(message)
Starts prompting the user until the target command is entered.

message (string, optional): The prompt message displayed to the user. Defaults to 'Enter command: '.
Returns a Promise that resolves with the target command when entered.

stop()
Manually stops the prompt and closes the readline interface.
Notes

The comparison of the input with the target command is case-insensitive.
Leading and trailing whitespace in the user input is trimmed.
The library uses the built-in Node.js readline module, so no external dependencies are required.

License
MIT License
