# 🧩 MonoNET  
### .NET Obfuscation Suite for Developers

MonoNET is a lightweight yet powerful **.NET obfuscator** built to protect managed assemblies from reverse engineering, tampering, and decompilation.  
It combines multiple advanced protection layers, a modern GUI, and dnlib integration to transform your assemblies into hardened, unreadable binaries — without breaking functionality.

---

## ⚙️ Overview

MonoNET takes your **.NET executable or DLL**, analyzes its IL structure, and applies a sequence of protection phases that distort and encrypt the code while maintaining its functionality.  
It’s built for developers who want strong protection without added dependencies or runtime overhead.

**Supported targets:**  
- .NET Framework  
- .NET Core  
- Unity (Mono/IL2CPP)  

---

## 🧠 How It Works

MonoNET loads your assembly using **dnlib**, processes it through a pipeline of protection modules, and then writes the obfuscated output assembly.  
Each protection layer targets different aspects of decompilation and reverse-engineering tools such as dnSpy, ILSpy, or JustDecompile.

**Protection flow example:**
1. Load assembly  
2. Apply Reference Proxy  
3. Apply Control Flow (optional stages)  
4. Apply Import & String protections  
5. Write protected output  

---

## 🔒 Protection Modules

### 🌀 Control Flow Obfuscation
- Breaks up the logical flow of methods using junk branches and opaque predicates.  
- Makes decompiled output messy and confusing.  
- **Modes:** `Light`, `Normal`, `Extreme`

### 🧩 Reference Proxy (RP)
- Redirects method calls through generated proxy methods.  
- Hides actual references and makes tracing call patterns very difficult.  
- **Modes:** `Normal`, `Strong`

### 🧠 String Encryption
- Encrypts string literals in your assembly.  
- Decrypts at runtime through dynamic routines.  
- Protects sensitive data like API keys, URLs, and messages.

### 🧮 Number Obfuscation
- Encodes integer and float constants using complex arithmetic.  
- Prevents tools from showing clear numeric values.

### 🧷 Import Protection
- Obfuscates method imports and external references.  
- Makes it harder to identify used libraries and dependencies.  
- Can optionally replace `calli` instructions with protected imports.

### ⚙️ Calli Virtualization
- Converts direct method calls into low-level `calli` instructions.  
- Removes method metadata visibility, confusing IL analyzers.

### 🧭 Namespace Scrambler *(New)*
- Randomizes or replaces all namespace names in your assembly.  
- Breaks logical namespace structure for decompilers and refactoring tools.  
- **Modes:**
  - *Simple:* Short randomized strings  
  - *Advanced:* Deep randomized hierarchies  
  - *Custom Length:* User-defined namespace name length

---

## 🪟 GUI Features

- **File Menu:** Load `.dll` or `.exe` assemblies  
- **Protection Menu:** Choose protection modes and strengths  
- **Log Console:** Real-time obfuscation log  
- **Progress Indicators:** Shows each protection phase status  

---

## 💡 Usage

1. **Load Assembly:**  
   Click **File → Load Assembly**, select your `.dll` or `.exe`.

2. **Select Protections:**  
   Toggle desired protections (Control Flow, Reference Proxy, String Encryption, etc.).

3. **Run Obfuscation:**  
   Press **Protect**, wait for the log to complete, and check the output file (e.g. `example.dll`).

4. **Done:**  
   Your protected binary is ready for release or distribution.

---

## 🧰 Built With

- **C# (.NET Framework)**  
- **WinForms UI**  
- **dnlib** (assembly manipulation)  

---

## 🧑‍💻 Author
**@currentlycracking**  
A project focused on modern, GUI-based .NET obfuscation and protection.

---

## ⚠️ Disclaimer
MonoNET is designed **for developers to protect their own applications**.  
Do not use it for malicious purposes or to hide unauthorized modifications of third-party software.

---
