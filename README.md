# 🧩 Insecure Object Deserialization & Gadget Lab

> An interactive cybersecurity lab demonstrating how unsafe object deserialization (Marshal/YAML) leads to Remote Code Execution (RCE), and how to safely parse and defend against deserialization exploits.

[![Author](https://img.shields.io/badge/Made%20by-cyber--atharv-00ffcc?style=flat-square&logo=github)](https://github.com/cyber-atharv)
[![Ruby](https://img.shields.io/badge/Ruby-3.2+-CC342D?style=flat-square&logo=ruby&logoColor=white)](https://www.ruby-lang.org)
[![Gem](https://img.shields.io/badge/gem-marshalsea-E9573F?style=flat-square&logo=rubygems&logoColor=white)](https://rubygems.org/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square)](LICENSE)

---

## 📌 What is Insecure Deserialization?

**Serialization** turns a programming object (like user state or session data) into a stream of bytes so it can be saved or sent over the network.
**Deserialization** takes those raw bytes and turns them back into a living object in memory.

### The Vulnerability Trap 💣
When applications reconstruct objects from untrusted user data, special magic methods (like `marshal_load`, `init_with`, or `method_missing`) are automatically executed. Attackers craft malicious serialized payloads containing "gadget chains" (a sequence of existing code methods connected together like falling dominoes) to achieve **Remote Code Execution (RCE)** without ever sending a shell script directly.

This lab, crafted by **cyber-atharv**, breaks down how gadget chains work, how to inspect serialized data *without* executing it, and how to build resilient runtime defenses.

---

## ✨ Lab Components

1. **Safe Byte Reader:** Parses `Marshal` and `YAML` streams statically without invoking or instantiating risky objects.
2. **Gadget Chain Explorer:** Analyzes loaded classes and maps potential gadget paths (entry points -> intermediaries -> dangerous execution sinks).
3. **Live Vulnerable Sinatra Target:** A test server where you can fire serialized payloads over HTTP to observe how the exploit executes and verify defense filters.
4. **Runtime Defense Guard:** Implements strict allowlists and method call interceptors to block unauthorized object restoration.

---

## 🚀 Quick Start

### 1. Install Lab Dependencies
```bash
cd deserialization-gadget-lab
bundle install
```

### 2. Run the Test Suites
```bash
rake test
```

### 3. Launch the Interactive Target Web Server
```bash
bundle exec ruby -Ilib target/app.rb
```
Now send sample payloads or inspect safe and malicious Marshal files in the lab environment!

---

## 🧠 Why I Built This

Insecure deserialization (CWE-502) is a critical vulnerability found across Ruby, Python (Pickle), PHP, and Java. Building a static binary parser and reproducing realistic gadget chains gave me a clear, practical understanding of object lifecycles, memory safety, and why simple regex filtering fails to protect against deserialization attacks.

---

## ⚠️ Responsible Use

> This lab is created strictly for defensive security research, vulnerability understanding, and secure coding training.

---

## 📜 Author & License

- **Author:** [cyber-atharv](https://github.com/cyber-atharv)
- **License:** Open source under the MIT / AGPL License.
