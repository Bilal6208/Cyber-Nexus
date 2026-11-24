# CyberNexus — Cybersecurity Knowledge Chatbot

CyberNexus is a console-based chatbot written in **C** that answers questions about three areas of cybersecurity: **Networking**, **Linux Commands** and **Cyber Threats**. Its knowledge base is a JSON dataset of 600 terms (200 per category), each with a definition and a real-world example. A Node.js server and a browser-based terminal-style GUI are also included on top of the same C program.

**Course:** CL1002 Programming Fundamentals (Lab), FAST-NUCES Karachi

**Submitted by:** Yasir (26K-2048), Bilal (26K-2049)

**Submitted to:** Miss Hijaab Sikander


---

## Features

- Loads 600 cybersecurity terms from `data.json` at run time
- Detects the topic of a question from free-text input (keyword matching)
- Shows a **definition** and an **example** for the matched term
- **Comparison mode:** compares two terms in one question (e.g. `compare tcp and udp`)
- Greeting and exit handling, and a clear message for unknown terms
- Browser GUI with quick-query buttons, connected to the C program through Node.js

---

## Test Cases

### Case 1: Single Term (Networking)

- **Description:** Tests whether the chatbot finds and displays a Networking term.
- **Inputs:** `what is dns`
- **Expected Output:** The definition and example of DNS are displayed.
- **Screenshot:**

<img width="700" height="450" alt="test-1-2-dns-tcp-udp" src="https://github.com/user-attachments/assets/795fd9f0-58d0-429b-99a0-33f0f57f4e8c" />

### Case 2: Comparison of Two Terms

- **Description:** Tests whether the chatbot can compare two terms in one question.
- **Inputs:** `compare tcp and udp`
- **Expected Output:** `COMPARISON: TCP vs UDP` is displayed, with `[01] TCP` and `[02] UDP`, each showing a definition and an example.
- **Screenshot:**

<img width="700" height="450" alt="test-1-2-dns-tcp-udp" src="https://github.com/user-attachments/assets/795fd9f0-58d0-429b-99a0-33f0f57f4e8c" />

### Case 3: Single Term (Cyber Threats)

- **Description:** Tests whether the chatbot finds and displays a Cyber Threats term.
- **Inputs:** `what is phishing`
- **Expected Output:** The definition and example of Phishing are displayed.
- **Screenshot:**

<img width="700" height="450" alt="test-3-4-phishing-grep" src="https://github.com/user-attachments/assets/857000ac-3d69-45e4-8388-716eb3a080e4" />

### Case 4: Single Term (Linux Commands)

- **Description:** Tests whether the chatbot finds and displays a Linux command.
- **Inputs:** `what does grep do`
- **Expected Output:** The definition and example of `grep` are displayed.
- **Screenshot:**

<img width="700" height="450" alt="test-3-4-phishing-grep" src="https://github.com/user-attachments/assets/857000ac-3d69-45e4-8388-716eb3a080e4" />

### Case 5: Unknown Term

- **Description:** Tests how the program handles a term that is not in the dataset.
- **Inputs:** `xyzabc`
- **Expected Output:** An "unable to answer" message is displayed and the program keeps running without crashing.
- **Screenshot:**

<img width="700" height="450" alt="test-5-6-unknown-exit" src="https://github.com/user-attachments/assets/f89956cb-6ac0-47c8-a429-90ed08a47a80" />


### Case 6: Quit Chat

- **Description:** Tests whether the user can exit the chatbot using an exit word.
- **Inputs:** `bye` (or `exit` / `quit`)
- **Expected Output:** A goodbye message is displayed and the program ends.
- **Screenshot:**

<img width="700" height="450" alt="test-5-6-unknown-exit" src="https://github.com/user-attachments/assets/f89956cb-6ac0-47c8-a429-90ed08a47a80" />


---

## User Guide

### Getting Started

1. Run `cybernexus.exe` (console) or `Run_GUI.bat` (browser GUI).
2. Type a greeting (`hi`, `hello` or `hey`) to load the dataset. Nothing else works until you do this.
3. When `You:` appears, type your question and press **Enter**.
4. Type `exit`, `quit` or `bye` to leave.

### What You Can Ask

| Category | Example terms |
|---|---|
| **Networking** | DNS, DHCP, IP Address, MAC Address, Subnet Mask, Router, Switch, Firewall, NAT, TCP, UDP, HTTP/HTTPS, VPN, VLAN, OSI Model, Latency, Bandwidth |
| **Linux Commands** | `ls`, `cd`, `pwd`, `mkdir`, `grep`, `chmod`, `chown`, `sudo`, `ps`, `top`, `kill`, `df`, `curl`, `wget`, `systemctl` |
| **Cyber Threats** | Phishing, Ransomware, Spyware, Trojan Horse, Rootkit, Keylogger, Botnet, SQL Injection, XSS, CSRF, DDoS, Man-in-the-Middle Attack, ARP Spoofing, Brute Force Attack, Zero-Day Exploit, Social Engineering |

### How to Ask

- **Single term:** `what is dns`, `explain what is router`, `what does mkdir do`, `phishing`
- **Comparison:** `compare tcp and udp`, `tcp vs udp`

### Example Questions

| You type | What you get |
|---|---|
| `hi` | Greeting message, dataset is loaded |
| `what is dns` | Definition and example of DNS |
| `explain what is router` | Definition and example of Router |
| `what does mkdir do` | Definition and example of `mkdir` |
| `what is ransomware` | Definition and example of Ransomware |
| `compare tcp and udp` | Side-by-side comparison of TCP and UDP |
| `xyzabc` | "Unable to answer" message |
| `bye` | Goodbye message, program ends |

### Messages You May See

| Message | Meaning |
|---|---|
| `Sorry, "..." I am unable to answer this question.` | The term is not in the dataset (GUI: "was not found in the database") |
| `[!] Record not found in database.` | One of the two compared terms was not found |
| `[Error] Could not load dataset. Exiting.` | `data.json` was not found; run the program from the `backend` folder |
| `Greetings file not found!` | `greetings.txt` is missing from the `data` folder |
| `Goodbye! Exiting session...` | You typed `exit`, `quit` or `bye` |

### Troubleshooting

- **Nothing happens after typing a question:** type `hi` first, because the dataset loads only after the greeting.
- **Dataset error on start:** run `cybernexus.exe` from inside the `backend` folder, so `../data/data.json` can be found.
- **`Run_GUI.bat` closes immediately or the page does not open:** check that Node.js is installed.
- **Wrong or unexpected answer:** try a longer, clearer term (e.g. `ip address` instead of `ip`), since very short keywords can match inside other words.

### Sample Output

```
You: what is dns

  [CyberNexus]: DNS
  Definition : ...
  Example    : ...
```

**Console output:**

<img width="500" height="250" alt="console-output" src="https://github.com/user-attachments/assets/4ae9c836-b9a6-4d34-ae80-4f55fdda06d4" />


### Tips and Limitations

- Only terms in the dataset can be answered; others show an "unable to answer" message.
- A maximum of **two terms** can be compared per question.
- Spelling must be correct (no fuzzy matching).
- Keep each question under 256 characters.
- Avoid the words `exit`, `quit` and `bye` inside a question, because they end the session.
- Very short keywords (`ls`, `id`, `ip`) can sometimes match inside longer words.

---

## Controls

- **hi / hello / hey** : Start the chatbot and load the dataset.
- **Any term or question** : Get its definition and example.
- **compare X and Y** : Compare two terms.
- **exit / quit / bye** : Quit the chatbot.

---

## Technologies Used

- **Programming Language:** C (backend), JavaScript / Node.js, HTML and CSS (GUI)
- **IDE / Code Editor:** Code::Blocks / Visual Studio Code
- **Compiler:** GCC (MinGW)
- **Operating System:** Windows
- **Libraries:** cJSON
- **Header Files:** stdio.h, stdlib.h, string.h, ctype.h, cJSON.h

---

## Project Structure

```
Project
├── backend
│   ├── main.c
│   ├── reader.c
│   ├── intent.c
│   ├── searching.c
│   ├── response.c
│   ├── cybernexus.exe
│   └── cJSON
│       ├── cJSON.c
│       └── cJSON.h
├── data
│   ├── data.json
│   └── greetings.txt
├── frontend
│   ├── index.html
│   ├── style.css
│   ├── app.js
│   └── server.js
└── Run_GUI.bat
```

---

## Code Structure

- **main():** Waits for the greeting, loads the dataset, runs the question loop, calls the other modules and handles exit.
- **load_dataset() / get_dataset_root()** (`reader.c`): Reads `data.json` into memory using cJSON and gives access to the loaded data.
- **detect_intent()** (`intent.c`): Converts the input to lower case, checks for exit words and matches up to two terms from the `KEYWORDS` array.
- **match_strings() / search_keyword()** (`searching.c`): Searches the Networking, Linux Commands and Cyber Threats categories with a case-insensitive exact match.
- **generate_response()** (`response.c`): Prints the definition and example, the comparison view, or the "unable to answer" message.

---

## Programming Concepts Used

- Arrays and arrays of strings
- Strings and string handling functions
- Loops and conditional statements
- User-defined functions split across multiple source files
- Pointers
- Dynamic memory allocation (`malloc` / `free`)
- File handling (`fopen`, `fread`, `fseek`)
- Variables and data types

---

## How to Run CyberNexus

### Console version

1. Open the `backend` folder in Code::Blocks or VS Code with a suitable C compiler (GCC / MinGW).
2. Compile `main.c` together with `cJSON/cJSON.c`:
   ```
   gcc main.c cJSON/cJSON.c -o cybernexus.exe
   ```
3. Run `cybernexus.exe` from inside the `backend` folder, so the `../data/` paths resolve correctly.
4. Type `hi` to start.
5. Ask a question, e.g. `what is dns` or `compare tcp and udp`.
6. Type `bye` to quit.

### Browser GUI version (using `Run_GUI.bat`)

**Step 1: Install Node.js**
Node.js must be installed before the GUI can start.


**Step 2: Double-click `Run_GUI.bat`**
This starts the Node.js server (`server.js`), which connects the browser to the C program (`cybernexus.exe`)


**Step 3: Wait for the server window**
A terminal window opens and shows that the server is running, along with the local address. Keep this window open while you use the chatbot.


**Step 4: Open the chatbot in your browser**
Open the local address shown in the terminal. The CYBER_BOT screen appears.

<img width="450" height="600" alt="gui-home" src="https://github.com/user-attachments/assets/b36574ce-21c2-4f4d-8f39-eb68a86be40e" />

**Step 5: Ask a question**
Type a question or click a quick-query button (DNS, TCP vs UDP, Phishing, Firewall, Linux: grep).

<img width="500" height="500" alt="gui-greeting-switch-bye" src="https://github.com/user-attachments/assets/323a71a8-6b76-4ccc-bdb8-721ce9c740cc" />

**Step 6: Close the chatbot**
Type `bye`, then close the browser tab and the terminal window to stop the server.

---

## Limitations and Future Enhancements

**Limitations**
- Only the 600 terms in `data.json` can be answered.
- Intent detection uses substring matching and understands keywords only, not sentence meaning.
- The GUI requires Node.js.

**Future enhancements**
- Fuzzy matching for spelling mistakes and word-boundary matching
- Self-learning from unanswered questions
- Practice mode with quizzes
- Live threat intelligence feeds (NVD, CISA, VirusTotal)

---
