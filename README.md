# Gammadyne G-Merge Language Support

VS Code language support for **Gammadyne Mailer G-Merge scripts**.

This extension provides syntax highlighting and basic language awareness for the proprietary G-Merge scripting language used in **Gammadyne Mailer** projects, helping developers write, read, and maintain Incoming and Outgoing scripts with more clarity and safety.

---

## ✨ Features

- Syntax highlighting for:
  - G-Merge script blocks `[[ ... ]]`
  - Variables (`_email`, `_now`, `_subject`, etc.)
  - Built-in functions (`db_add_row`, `db_acquire_row`, `str_contains`, `disregard`, etc.)
  - Control structures (`if`, `else`, `endif`, `var`)
  - Comments (`; comment`)
- Automatic language detection for:
  - `.gmerge` files
  - Gammadyne script files
- Improved readability of complex Incoming Scripts
- Safer editing of production email processing logic

---

## 📂 Supported File Types

| File Extension | Description                         |
| -------------- | ----------------------------------- |
| `.gmerge`      | G-Merge script files                |
| `.txt`         | (Optional) When manually associated |

You can manually associate the language if needed:

1. Open a file
2. Click the language mode in the bottom-right corner
3. Select **Gammadyne G-Merge**

---

## 🚀 Getting Started

1. Install the extension from the VS Code Marketplace
2. Open a G-Merge script file
3. Enjoy improved readability and structure 🎉

---

## 🧠 What is G-Merge?

**G-Merge** is a proprietary scripting language used by **Gammadyne Mailer** to:

- Process incoming emails
- Extract and normalize email addresses
- Apply filtering and validation rules
- Insert or update records in databases (ODBC / SQLite / SQL Server)
- Automate email list management

This extension does **not** execute scripts — it only provides editor support.

---

## ⚠️ Limitations

- No code execution or validation
- No autocomplete (yet)
- No linting (planned for future versions)

---

## 🛣️ Roadmap

Planned improvements:

- Autocomplete for built-in functions
- Snippets for common patterns
- Basic linting (syntax warnings)
- Documentation hover hints

---

## 🤝 Contributing

Contributions are welcome!

Feel free to:

- Open issues
- Submit pull requests
- Suggest improvements or new features

---

## 📜 License

MIT License

---

## 🔗 Related

- [GitHub Repository](https://github.com/jmpin-nexus/gammadyne-gmerge-vscode)
- [Gammadyne Mailer](https://www.gammadyne.com/)
- G-Merge documentation (official)
- [How to Create and Publish VS Code Extensions](doc/Publishing-VSCode-Extension.md)
- [Git Tags Best Practices for VS Code Extensions](doc/git-tags-best-practice.md)

---

## 🧑‍💻 Author

Developed by **Jose Maria Villac Pinheiro**  
Focused on safe, scalable email automation and data processing.
