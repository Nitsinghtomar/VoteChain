# 🗳️ VoteChain - Secure Blockchain E-Voting Platform with Biometric Authentication

Modern democratic processes require robust security measures to ensure election integrity and prevent fraud. VoteChain delivers a comprehensive **blockchain-powered e-voting solution** that combines **distributed ledger technology** with **facial recognition biometrics** to create an immutable and secure voting environment.

The system architecture utilizes **MongoDB** as the primary database, organized into three core collections:
- `users`: manages voter profiles and biometric facial encodings
- `candidates`: maintains candidate registration and details
- `elections`: oversees election lifecycle and historical records

This platform provides organizations, educational institutions, and communities with a trustworthy, technology-enhanced democratic voting solution.

## 📁 Project Architecture

The codebase follows a modular design pattern with clear separation of concerns across frontend, backend, and blockchain components:

```
Secure-Blockchain-E-Voting-Platform/
│
├── client/                 # Frontend application for user interaction and voting interface
├── server/                 # Backend services for authentication, biometrics, and API management
├── smart_contract/         # Ethereum smart contracts for decentralized vote recording
│
├── dlib-*.whl              # Dlib library package for facial recognition (Windows compatible)
├── package.json            # Root project configuration and dependency management
├── readme.md               # Comprehensive project documentation
```

### 🔍 Component Overview

- **`client/`**:  
  Frontend interface built for voter registration, authentication, candidate selection, and results viewing.

- **`server/`**:  
  Backend infrastructure handling user authentication, facial recognition processing, database operations, and blockchain communication.

- **`smart_contract/`**:  
  Solidity-based smart contracts deployed on Ethereum-compatible networks for transparent and immutable vote storage.

- **`dlib-*.whl`**:  
  Pre-compiled Dlib library optimized for Windows environments, essential for facial recognition capabilities.

- **`package.json`**:  
  Project configuration file containing dependencies, scripts, and metadata for Node.js ecosystem.

---

## ⚡ Quick Start Guide

Follow these comprehensive steps to deploy and configure the **Secure Blockchain E-Voting Platform with Biometric Authentication**.

---

### 🛠️ Prerequisites and Installation

#### � Database Configuration
1. Navigate to `/server/.env` and configure your MongoDB connection string on **line 2**.
2. The system will automatically initialize database collections (`users`, `candidates`, `elections`) using the schema definitions in `/server/Models`.

#### 📧 Email Service Integration
1. Set up email service credentials (recommended: Gmail with app-specific password).
2. Generate an **application password** following your email provider's security guidelines.
3. Configure EMAIL and PASSWORD variables in `/server/.env` for automated notifications.

---

### ⛓️ Blockchain Infrastructure Setup

#### 🔧 Local Blockchain Environment (Ganache)
1. Download and install [Ganache](https://trufflesuite.com/ganache/) for local blockchain simulation.
2. Launch Ganache to access 10 pre-funded Ethereum accounts (each with 100 ETH).
3. Configure `/smart_contract/truffle-config.js` to connect with your Ganache instance.

#### 🦊 Wallet Integration (MetaMask)
1. Install the [MetaMask browser extension](https://metamask.io/) for transaction management.
2. Import a test account using private keys from your Ganache setup.
3. Configure MetaMask to interact with your local blockchain network.

#### 📝 Smart Contract Deployment
```bash
cd smart_contract
npm install -g truffle      # Install Truffle framework globally (if not already installed)
truffle compile             # Compile smart contracts
truffle migrate             # Deploy contracts to blockchain
```
4. Post-deployment configuration:
   - Copy the deployed contract **address** to `client/utils/Constant.js`.
   - Transfer the `Transaction.json` ABI file from `smart_contract/build/contracts/` to `client/utils/Transaction.json`.

---

### 🔍 Biometric Recognition Setup

#### 🐍 Python Dependencies
Install required packages for facial recognition functionality:

```bash
pip install opencv-python numpy os face_recognition
```

> **Troubleshooting**: If `face_recognition` installation fails, manually install the dlib dependency:
```bash
pip install dlib-19.24.99-cp312-cp312-win_amd64.whl
```
> **Alternative Solution**: If issues persist, try downgrading `numpy` to ensure compatibility.

#### � Facial Encoding Configuration
1. Place user reference images in the `/server/Faces/` directory.
2. Ensure image filenames correspond to user identifiers in your database.
3. Update the photo directory path in `/server/Controller/encoded.py` at **line 6** if necessary.

---

### 🚀 Application Deployment

#### Frontend Setup
```bash
cd client
npm install
npm run start
```

#### Backend Setup
```bash
cd server
npm install
nodemon main
```

Allow a few moments for both services to initialize, then access the application through your web browser to begin the secure voting process.

---

## 🌟 Key Features

This platform integrates cutting-edge security technologies to deliver a comprehensive and trustworthy voting experience.

- 🔐 **Immutable Blockchain Records**  
  Guarantees vote integrity through decentralized ledger technology that prevents tampering and ensures transparency.

- 🎯 **Advanced Biometric Verification**  
  Employs sophisticated facial recognition algorithms to authenticate voter identity before ballot access.

- � **Intuitive Voting Interface**  
  Provides a seamless user experience for vote casting, candidate review, and real-time election monitoring.

- � **Automated Notification System**  
  Sends instant confirmation emails upon successful registration and vote submission.

- 📊 **Decentralized Vote Recording**  
  Utilizes Ethereum smart contracts to maintain transparent and verifiable election records.

- 🎛️ **Comprehensive Administration Dashboard**  
  Enables election management, result aggregation, and system oversight through an intuitive admin interface.

---

## 💻 Technology Stack

### 🔧 Backend Infrastructure
- **Node.js** – Scalable server-side runtime environment
- **Express.js** – Lightweight web application framework
- **MongoDB** – Document-oriented database for flexible data storage
- **Dlib + face_recognition** – State-of-the-art facial recognition engine
- **Python** – Advanced image processing and biometric encoding

### 🎨 Frontend Development
- **React.js** – Modern component-based user interface framework
- **MetaMask** – Secure Web3 wallet integration for blockchain transactions

### ⛓️ Blockchain Technology
- **Solidity** – Smart contract programming language for Ethereum
- **Truffle** – Comprehensive Ethereum development and testing framework
- **Ganache** – Personal blockchain for rapid development and testing

### �️ Development Tools
- **Nodemon** – Automatic server restart for development efficiency
- **dotenv** – Secure environment variable management
- **SMTP Integration** – Automated email notifications and verification

---



