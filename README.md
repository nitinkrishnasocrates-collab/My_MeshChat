# My_MeshChat
MeshChat is a decentralized, peer-to-peer messaging application that enables users to communicate directly without relying on centralized servers or internet connectivity (when supported by the configured mesh network)
# MeshChat

**Offline-First Messaging Application**

MeshChat is a Python-based messaging project designed to enable communication between nearby devices without requiring internet access. It aims to support communication through TCP/LAN, Bluetooth, and peer-to-peer mesh networking.

## Features

- Offline communication over supported local connections.
- TCP-based real-time messaging.
- Multiple client connections.
- Bluetooth communication (Stage 1).
- Contact management (planned).
- Persistent chat history (planned).
- Electron desktop application (planned).
- Peer-to-peer mesh networking (under development).

## Technology Stack

- Python – Backend and networking.
- TCP Sockets – Local network communication.
- Bluetooth – Nearby device connectivity.
- Electron – Planned desktop application.
- React and TypeScript – Planned frontend.
- SQLite – Planned persistent storage.

## Project Structure

```text
MeshChat/
│
├── bluetooth/
├── client/
│   └── tcp_client.py
├── database/
├── docs/
├── mesh/
├── mobile/
├── network/
├── protocol/
├── security/
├── server/
│   └── tcp_server.py
├── tests/
│
├── check_env.py
├── requirements.txt
└── README.md
```

## Installation and Setup

### Requirements

- Windows 10/11
- Python 3.10 or later
- PowerShell

### 1. Clone the repository

```powershell
git clone <YOUR-GITHUB-REPOSITORY-URL>
```

### 2. Navigate to the project folder

```powershell
cd MeshChat
```

### 3. Create a virtual environment

```powershell
python -m venv .venv
```

### 4. Activate the virtual environment

```powershell
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks activation, run:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\.venv\Scripts\Activate.ps1
```

### 5. Install dependencies

```powershell
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 6. Check the environment

```powershell
python .\check_env.py
```

## Running MeshChat

MeshChat currently uses a central TCP server to relay messages between connected clients.

### Step 1: Start the TCP server

Open the first PowerShell terminal:

```powershell
cd MeshChat
.\.venv\Scripts\Activate.ps1
python .\server\tcp_server.py
```

Keep the server terminal running.

### Step 2: Connect the first user

Open a second PowerShell terminal:

```powershell
cd MeshChat
.\.venv\Scripts\Activate.ps1
python .\client\tcp_client.py --name Nitin
```

### Step 3: Connect another user

Open a third PowerShell terminal:

```powershell
cd MeshChat
.\.venv\Scripts\Activate.ps1
python .\client\tcp_client.py --name Friend
```

You can now exchange messages between the connected clients.

Type `/quit` to leave the chat.

Press `Ctrl+C` in the server terminal to stop the server.

## Connecting Multiple Computers

To communicate between two computers:

1. Connect both computers to the same Wi-Fi/LAN.
2. Start the TCP server on one computer.
3. Find that computer's local IP address using:

```powershell
ipconfig
```

4. On the second computer, connect using the server's LAN IP:

```powershell
python .\client\tcp_client.py --name Friend --host SERVER_IP
```

Replace `SERVER_IP` with the server computer's actual IPv4 address.

Ensure Windows Firewall allows the server to receive TCP connections on port `5050`.

## Current Limitations

- The current Stage 2 implementation uses a central TCP relay.
- Devices need a supported network connection to communicate.
- Internet access is not required for same-LAN communication.
- Messages are not currently encrypted, saved, or forwarded while offline.
- Full decentralized peer-to-peer mesh networking is still under development.
- Electron desktop integration and persistent contact management are planned features.

## Future Development

- Electron desktop application.
- Permanent contact management.
- SQLite-based chat history.
- Bluetooth messaging integration.
- Peer-to-peer mesh communication.
- Message encryption.
- File sharing.
- Desktop notifications.

## Project Vision

To develop a reliable offline-first messaging platform that enables people to communicate directly with nearby devices without depending on traditional internet infrastructure.

---

**MeshChat – Connect Locally. Communicate Freely.**
