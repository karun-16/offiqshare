# OffiqShare

### Drop. Connect. Send Anything.

OffiqShare is a browser-based peer-to-peer file-sharing platform that lets users transfer files between devices without creating accounts or uploading file contents to cloud storage.

Share files using QR codes, six-character session codes, or shareable links.

**Live Demo:** https://offiqshare.onrender.com

---

## ✨ Features

- **Peer-to-Peer File Transfer** — Transfer files directly between connected devices using WebRTC.
- **QR Code Sharing** — Connect devices by scanning a QR code.
- **Session Codes** — Join a transfer using a six-character code.
- **Shareable Links** — Share a link that opens the receiving flow.
- **Multiple File Transfer** — Select and send multiple files.
- **Receiver Approval** — Preview incoming files and accept or reject a transfer.
- **Transfer Progress** — Track file-transfer progress and speed.
- **Transfer History** — Review previous transfers locally.
- **Transfer Recovery** — Support for resuming interrupted transfers.
- **Responsive Interface** — Use the web application on supported desktop and mobile browsers.
- **Windows Desktop App** — Access a native desktop version through the official installer.

---

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| Frontend | HTML, CSS, JavaScript |
| Backend | Node.js, Express.js |
| Real-time Signaling | WebSockets (`ws`) |
| File Transfer | WebRTC Data Channels |
| QR Codes | QRCode.js |
| Session Management | In-memory server storage |
| Desktop Application | Tauri 2.x (separate desktop project) |
| Web Deployment | Render |
| Desktop Distribution | GitHub Releases |

**Database:** No persistent server database is used for transfer sessions. Session information is maintained in server memory and expires automatically.

**Authentication:** User accounts and login are not required.

---

## 🏗️ How It Works

1. The sender selects files and creates a transfer session.
2. OffiqShare generates a QR code, session code, and shareable link.
3. The receiver opens the link or enters the session code and reviews the incoming files.
4. After the receiver accepts, the devices establish a peer-to-peer WebRTC connection.
5. Files are transferred through a WebRTC data channel rather than uploaded to the signaling server.

The signaling server coordinates connections and exchanges session information. WebRTC encrypts data in transit; actual connection availability and transfer performance depend on the devices and network.

---

## 🚀 Run Locally

### Prerequisites

- Node.js 18 or later
- npm

### Installation

Clone the repository:

```bash
git clone https://github.com/karun-16/offiqshare.git
cd offiqshare
