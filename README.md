Secure Offline Communication App
This project is a secure, decentralized, offline communication application designed for environments with no internet connectivity, leveraging a mesh network of devices. It is built with Python, FastAPI, SQLite, and Tkinter.

Project Overview
The application enables users to communicate securely in offline environments by creating a peer-to-peer mesh network using Wi-Fi Direct or Bluetooth. Messages are end-to-end encrypted and hop from device to device until they reach their intended recipient.

Key Features
Offline Communication: Works without any internet infrastructure.

Mesh Networking: Devices act as nodes to relay messages for other devices.

End-to-End Encryption: Uses a combination of AES-256 and RSA for military-grade security.

Ephemeral Messaging: Messages are deleted from devices after being read.

Decentralized: No central server, making it resilient to single points of failure.

Tech Stack
Backend: FastAPI

Frontend: Tkinter

Database: SQLite (for temporary local storage)

Networking: Wi-Fi Direct / Bluetooth (via Python libraries)

Security: AES-256 & RSA (using the cryptography library)

Project Structure
secure-offline-app/
│
├── .gitignore
├── main.py
├── README.md
└── requirements.txt

Setup and Installation
Clone the repository:

git clone <repository-url>
cd SecureLink

Create a virtual environment:

python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`

Install the dependencies:

pip install -r requirements.txt

Run the application:

python main.py

How It Works
Device Discovery: The application will scan for nearby devices that are also running the app.

Peer-to-Peer Connection: Users can initiate a connection with a discovered device, forming the basis of the mesh network.

Message Encryption: Before a message is sent, it's encrypted with the recipient's public key (RSA), and the message content itself is encrypted with AES-256.

Message Routing: The application will use a simple routing algorithm to forward the message to the node that is "closest" to the recipient in the mesh network.

Temporary Storage: Messages are stored temporarily in a local SQLite database until they are successfully forwarded or delivered.

Auto-Deletion: Once a message is confirmed as read by the recipient, it is securely deleted from all intermediate nodes and the sender's device.