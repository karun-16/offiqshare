# 🚀 OffiqShare

### 🔗 Drop. Connect. Send Anything.

**OffiqShare** is a modern, browser-based peer-to-peer file-sharing platform that makes transferring files between devices simple, fast, and convenient. Connect devices using a QR code, a six-character session code, or a shareable link — without creating an account or uploading file contents to a central cloud storage service.

🌐 **Live Website:** https://offiqshare.onrender.com/

💻 **Windows Desktop App:** [Download the latest release](https://github.com/karun-16/offiqshare-/releases/latest/download/OffiqShare_Setup.exe)

📦 **Source Code:** [GitHub Repository](https://github.com/karun-16/offiqshare)

---

## ✨ Features

- 🔄 **Peer-to-Peer File Sharing** — Transfer files directly between connected devices using WebRTC.
- 📱 **QR Code Connection** — Scan a QR code to connect devices quickly.
- 🔢 **Six-Character Session Code** — Join a transfer using a simple session code.
- 🔗 **Shareable Links** — Generate a link to simplify the receiving process.
- 📁 **Multiple File Transfers** — Select and send multiple files in a transfer session.
- 🛡️ **Receiver Approval** — Allow the receiver to review and accept or reject incoming files.
- 📊 **Live Transfer Progress** — Monitor transfer progress and speed.
- ⏸️ **Transfer Recovery** — Support for recovering interrupted transfers where the connection and application state allow it.
- 🕘 **Transfer History** — Review transfer history stored by the client.
- 📲 **Cross-Device Experience** — Use the web application on supported desktop and mobile browsers.
- 🖥️ **Windows Desktop Application** — Access OffiqShare through a dedicated desktop app.
- 🔔 **Desktop Update Checking** — The desktop application can check for newer releases.
- 🎨 **Simple User Interface** — A straightforward interface designed to make file sharing easy.
- 🔐 **No Account Required** — Start sharing without creating a user account.

---

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| 🎨 Frontend | HTML5, CSS3, JavaScript |
| ⚙️ Backend | Node.js |
| 🌐 Web Framework | Express.js |
| 🔌 Real-Time Communication | WebSockets using `ws` |
| 🔗 Peer-to-Peer Connectivity | WebRTC |
| 📡 File Transfer | WebRTC Data Channels |
| 📷 QR Code Generation | QRCode.js |
| 🆔 Session Identifiers | UUID |
| 🖥️ Desktop Framework | Tauri 2.x |
| ☁️ Web Hosting | Render |
| 📦 Desktop Releases | GitHub Releases |
| 🗃️ Session Storage | In-memory server storage |

---

## 🔍 How OffiqShare Works

OffiqShare uses WebRTC for peer-to-peer file transfers and a WebSocket-based signaling server to help devices establish a connection.

```text
             📤 SENDER DEVICE
                    |
                    v
           🔗 Create a Session
                    |
          +---------+---------+
          |         |         |
          v         v         v
       📷 QR      🔢 Code    🔗 Link
          |         |         |
          +---------+---------+
                    |
                    v
             📥 RECEIVER DEVICE
                    |
                    v
           🛡️ Accept the Transfer
                    |
                    v
           🤝 Establish WebRTC
                    |
                    v
          🔄 Peer-to-Peer Transfer
                    |
                    v
             ✅ Files Received
```

### 📌 Transfer Workflow

1. 📤 **Create a session:** The sender selects files and initiates a sharing session.
2. 🔗 **Share connection details:** OffiqShare provides a QR code, session code, or shareable link.
3. 📥 **Connect the receiver:** The receiving device opens the link or joins with the session code.
4. 🛡️ **Approve the transfer:** The receiver reviews the incoming files and accepts or rejects the request.
5. 🤝 **Establish a connection:** The devices negotiate a WebRTC connection through the signaling server.
6. 📦 **Transfer files:** File data travels through the WebRTC data channel when the peer-to-peer connection is established.
7. ✅ **Complete the transfer:** The receiver gets the files, and the application updates the transfer status.

**Important:** The signaling server coordinates connection setup; it is not intended to act as a cloud storage service for file contents. Network conditions and firewall restrictions can affect whether a peer-to-peer connection succeeds.

---

## 🏗️ Project Architecture

OffiqShare consists of a frontend, a Node.js signaling server, and a WebRTC-based file-transfer mechanism.

### 🎨 Frontend

The frontend provides the user interface and handles the user's transfer workflow.

- Displays the file-sharing interface.
- Generates and presents connection details.
- Handles QR codes, session codes, and shareable links.
- Coordinates sender and receiver interactions.
- Displays file-transfer progress and status.

### ⚙️ Backend

The backend runs on Node.js and Express.js, with WebSockets for real-time signaling.

- Serves the web application.
- Creates and manages temporary sharing sessions.
- Exchanges WebRTC signaling messages between connected clients.
- Helps peers negotiate connections.
- Maintains session information in server memory.

### 🔄 Peer-to-Peer Transfer

WebRTC Data Channels carry file data between connected devices. This reduces the need to route file contents through the application's server.

---

## 📂 Project Structure

```text
offiqshare/
│
├── 📁 public/
│   ├── 📁 css/
│   │   └── 🎨 Stylesheets
│   │
│   ├── 📁 js/
│   │   ├── 🔌 connection.js
│   │   └── 📦 transfer.js
│   │
│   ├── 🌐 index.html
│   └── ⬇️ download.html
│
├── 📁 server/
│   ├── ⚙️ index.js
│   ├── 📦 package.json
│   └── 🔒 package-lock.json
│
└── 📄 .gitignore
```

| File or Directory | Purpose |
|---|---|
| `public/` | Frontend pages, stylesheets, and client-side scripts |
| `public/css/` | Styling and layout |
| `public/js/connection.js` | Connection and WebRTC signaling logic |
| `public/js/transfer.js` | File-transfer handling and progress updates |
| `public/index.html` | Main file-sharing interface |
| `public/download.html` | Desktop download page |
| `server/index.js` | Express server and WebSocket signaling |
| `server/package.json` | Server dependencies and run scripts |
| `.gitignore` | Files and directories excluded from Git |

*Note: The Windows desktop application's source code is maintained separately from this web repository.*

---

## 🚀 Run OffiqShare Locally

Want to explore the source code or run your own development instance? Follow these steps.

### 📋 Prerequisites

Install the following before starting:

- [Node.js](https://nodejs.org/) — Version 18 or later
- npm — Included with Node.js
- [Git](https://git-scm.com/) — To clone the repository
- A modern browser with WebRTC support

### 1️⃣ Clone the Repository

Open a terminal and run:

```bash
git clone https://github.com/karun-16/offiqshare.git
cd offiqshare
```

### 2️⃣ Install Dependencies

```bash
cd server
npm install
```

### 3️⃣ Start the Development Server

```bash
npm run dev
```

### 4️⃣ Open the Application

Visit the following address in your browser:

🌐 **http://localhost:3000**

To run the server without watch mode, use:

```bash
npm start
```

**Troubleshooting tip:** If port `3000` is already in use, stop the other process or configure an available port if the server supports it. For peer-to-peer transfers, ensure the participating devices can establish WebRTC connections.

---

## 🔐 Privacy and Security

Privacy is an important part of OffiqShare's design.

- 👤 **No Account Registration:** Users do not need to create accounts to share files.
- ☁️ **No Intended Cloud Storage:** File contents are transferred peer-to-peer rather than intentionally uploaded to a central file-storage service.
- 🔗 **WebRTC Communication:** File transfers use WebRTC Data Channels.
- 🔒 **Encryption in Transit:** WebRTC protects data in transit using its built-in security mechanisms.
- ⏳ **Temporary Sessions:** Sharing-session information is maintained in server memory and expires automatically.
- 🗂️ **No Persistent Session Database:** The web server does not use a persistent database for its temporary transfer sessions.

### ⚠️ Security Considerations

- Share session codes and links only with intended recipients.
- Session metadata and connection details are processed by the signaling server.
- Peer-to-peer connectivity may be affected by firewalls, NAT configurations, or restrictive networks.
- Transfer history stored by the client may remain on the device until cleared.
- Avoid transferring sensitive files on untrusted devices or networks.

OffiqShare's peer-to-peer design reduces reliance on centralized file storage, but it does not eliminate every privacy or security risk.

---

## 🖥️ OffiqShare for Windows

Prefer a desktop experience? Download the Windows installer.

### ⬇️ Download

**[Download OffiqShare for Windows](https://github.com/karun-16/offiqshare-/releases/latest/download/OffiqShare_Setup.exe)**

The desktop application provides a dedicated Windows experience, desktop-specific interface behavior, and update checking.

📌 Desktop application releases are maintained separately from this web application's source repository.

---

## 🌐 Try It Online

You can use the deployed web application without cloning or installing the project.

👉 **[Launch OffiqShare](https://offiqshare.onrender.com/)**

Open the website on supported devices and follow the on-screen instructions to create or join a transfer session.

---

## 🛣️ Future Roadmap

OffiqShare is an evolving project, with potential improvements including:

- 📱 Native Android application
- 🍎 Native iOS application
- 🖥️ Expanded desktop platform support
- 🌍 Improved connectivity across restrictive networks
- ⚡ Further transfer performance and reliability improvements
- 🛡️ Additional security and privacy enhancements
- 🎨 Continued user-interface improvements

*These are planned or potential improvements, not a statement that they have already been implemented.*

---

## 🤝 Contributing

Contributions, suggestions, and bug reports are welcome!

1. 🍴 Fork the repository.
2. 🌿 Create a feature branch.
3. 💻 Make and test your changes.
4. 📤 Push your branch.
5. 🔀 Open a pull request describing your changes.

For bug reports, include steps to reproduce the issue, your browser or operating system, and any relevant error messages. Do not include private session codes or sensitive file contents.

---

## 👨‍💻 Author

**Karun Sarma**

- 🐙 GitHub: [@karun-16](https://github.com/karun-16)
- 🌐 Website: [OffiqShare](https://offiqshare.onrender.com/)
- 🏢 Organization: EnclaveEdge Technologies

---

## 📜 License

No license information is specified here. Before others reuse, modify, or redistribute this project, add a `LICENSE` file describing the permissions and conditions you want to apply.

---

<div align="center">

### 💙 Built to Make File Sharing Simpler

**OffiqShare — Drop. Connect. Send Anything.**

🌐 [Website](https://offiqshare.onrender.com/) · 💻 [GitHub Repository](https://github.com/karun-16/offiqshare)

</div>
