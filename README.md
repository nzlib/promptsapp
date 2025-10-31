# promptsapp

A lightweight Node.js command-line prompt helper that simplifies building interactive console applications.  
It allows you to define custom commands, handle user input dynamically, and specify an exit command — all with minimal setup.

---

## ✨ Features

- Simple and lightweight (no external dependencies)
- Works directly with Node.js’ built-in `readline` module
- Supports custom commands with arguments
- Easily configurable exit command and callback
- Ideal for CLI tools, chatbots, or REPL-style interfaces

---

## 📦 Installation

```bash
npm install promptsapp
```

Or include it directly in your project:

```bash
# If you cloned this repository
npm install
```

---

## 🚀 Usage Example

Here’s a quick example showing how to use `promptsapp`:

```js
const { app } = require('promptsapp');

const work = async (command, args) => {
  if (command === 'say') {
    console.log('You said:', args.join(' '));
  } else {
    console.log('Unknown command:', command);
  }
};

const prompt = app('Enter command (type "exit" to quit): ', 'exit', work);

prompt.onExit(() => {
  console.log('Goodbye!');
});

prompt.start();
```

**Output Example:**
```
Enter command (type "exit" to quit): say hello world
You said: hello world
Enter command (type "exit" to quit): test
Unknown command: test
Enter command (type "exit" to quit): exit
Goodbye!
```

---

## 🧩 API Reference

### `app(message, targetCommand, work)`

Creates a new prompt application instance.

| Parameter | Type | Description |
|------------|------|-------------|
| `message` | `string` | Message displayed for user input |
| `targetCommand` | `string` | Command that triggers program exit |
| `work` | `function(command, args)` | Async function that handles each command |

**Returns:** `promptsapp` instance.

---

### `promptsapp.start()`

Starts the interactive prompt loop.  
Returns a Promise that resolves when the exit command is entered.

---

### `promptsapp.stop()`

Stops the readline interface manually.

---

### `promptsapp.onExit(callback)`

Registers a callback that runs when the exit command is triggered.

---

## 🧠 Example Use Cases

- Build your own mini shell or REPL tool  
- Create chat-like terminal interfaces  
- Quickly prototype CLI apps

---

## 🧾 License

MIT License © 2025 [Your Name]

---

## 💬 Contributing

Contributions, issues, and feature requests are welcome!  
Feel free to open an issue or submit a pull request on [GitHub](https://github.com/yourusername/promptsapp).

---

## ⭐ Acknowledgements

Built with ❤️ using Node.js.
