---
layout: post
title: "Essential Bash Shortcuts and Mouse Tips for macOS Terminal Power Users"
date: 2025-06-07
categories: [macOS, Bash, Terminal, Productivity]
tags: [bash, mac, terminal, cli, shortcuts, developer-tools]
---

Whether you're navigating code, wrangling logs, or building scripts, mastering your terminal workflow is a **developer superpower**. If you spend hours in your terminal on macOS, this post is your cheat sheet for **Bash command line shortcuts and mouse tips** that can drastically boost your productivity.

---

## 🔑 Must-Know Bash Keyboard Shortcuts

These work in most macOS terminal emulators (Terminal.app, iTerm2, etc.) and are built into GNU Readline, which Bash uses for line editing.

| Shortcut   | Description                                            |
| ---------- | ------------------------------------------------------ |
| `Ctrl + A` | Move cursor to the **start** of the line               |
| `Ctrl + E` | Move cursor to the **end** of the line                 |
| `Ctrl + U` | **Delete** from cursor to the beginning of the line    |
| `Ctrl + K` | **Delete** from cursor to the end of the line          |
| `Ctrl + W` | Delete the **word** before the cursor                  |
| `Ctrl + L` | Clear the screen (same as `clear` command)             |
| `Ctrl + C` | **Cancel** the current command                         |
| `Ctrl + D` | **Logout** or exit shell / delete character at cursor  |
| `Ctrl + Y` | **Paste** the last killed (deleted) text               |
| `Alt + B`  | Move back **one word**                                 |
| `Alt + F`  | Move forward **one word**                              |
| `Ctrl + R` | Reverse search command history (start typing to match) |
| `!!`       | Run the **previous command**                           |
| `!$`       | Run the **last argument** of previous command          |

---

## 🖱️ Mouse and UI Tips for macOS Terminal

These are small things that make a huge difference, especially on Mac.

### 1. **Triple Click to Select the Entire Line**
Triple-clicking anywhere on a line in Terminal selects the whole command — useful for copying multi-line output or logs.

### 2. **Option + Drag for Rectangular Selection (iTerm2)**
Using [iTerm2](https://iterm2.com/)? Hold **Option** while dragging to select text **vertically** (column mode) — handy for copying logs or data in columns.

### 3. **Option + Click to Move Cursor (macOS Terminal & iTerm2)**
Click anywhere while holding **Option** to move your cursor directly to that position — no arrow keys needed!

> Works in both `Terminal.app` and iTerm2. A hidden gem for fast editing.

### 4. **Double Click to Select a Word**
Useful when you want to copy just part of a file path, variable name, or command.

### 5. **Command + Click to Open Links or Paths**
In iTerm2 or Terminal, if you see a file path or URL, `Cmd + Click` will open it in the default app or editor.

Example:
```bash
vim ~/Projects/myapp/main.py
````

You can `Cmd + Click` `main.py` to open in VS Code or your preferred editor.

### 6. **Copy with Mouse, Paste with Cmd + V**

On macOS Terminal:

* Select text with the mouse (auto-copies it)
* Press `Cmd + V` to paste — or right-click and choose **Paste**

> ⚠️ In `Terminal.app`, `Cmd + V` may not always work as expected for pasting large content. iTerm2 handles this better.

---

## 🛠️ Bonus Tips for a More Productive Shell

### Enable Mouse Support in `less`

Add this to your `~/.bash_profile` or `~/.zshrc` if you use `less` a lot:

```bash
export LESS='-R --mouse'
```

### Use `pbcopy` and `pbpaste`

Copy output directly from command line:

```bash
cat file.txt | pbcopy
pbpaste > newfile.txt
```

### Use Aliases for Long Commands

```bash
alias gs='git status'
alias ll='ls -alF'
```

### Use `open` Command to Launch Files from CLI

On macOS:

```bash
open .
open somefile.txt
```

This will open the current directory or file with the default app (Finder, VS Code, etc.).

---

## 🚀 TL;DR – Speed Up Your Terminal Life

* **Navigate smarter**: `Ctrl + A`, `Ctrl + E`, `Alt + B/F`
* **Edit faster**: `Ctrl + U/K/W`, `Ctrl + Y`
* **Search history**: `Ctrl + R`
* **Use the mouse efficiently**: triple-click, Option-click, Option-drag
* **Mac clipboard integration**: `pbcopy`, `pbpaste`
* **Open files fast**: `Cmd + Click` or `open <file>`

Once you commit these to muscle memory, you’ll feel like a **terminal ninja**. Happy hacking!