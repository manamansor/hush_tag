# HReport_KrM Review Copy.xlsxush Tag

Hush Tag is a decentralized ticketing system built on the Mina Protocol using zero-knowledge proofs. It allows for secure ticket generation and validation with privacy-preserving features.

## Features

- **Secure Ticket Generation**: Create unique tickets backed by the Mina blockchain.
- **QR Code Tickets**: Each ticket is represented by a QR code containing a public key.
- **Validation System**: Validate tickets and detect if they have been used before.
- **Simple UI**: Clean, responsive interface for both generating and validating tickets.

## Technology Stack

- **Frontend**: HTML, CSS, JavaScript
- **Backend**: Node.js, Express.js, TypeScript
- **Blockchain**: Mina Protocol with o1js
- **Zero-Knowledge Proofs**: Implemented via o1js Smart Contracts
- **QR Code**: QR code generation and reading with qrcode.js, jsqr and sharp

## Prerequisites

- **Node.js** (v18.14.0 or higher)
- **NPM** or **Yarn**

## Installation

1. Clone the repository:
   ```bash
    git clone https://github.com/Lantsov-Pavel/hush_tag.git
   
2. Navigate to the project directory:
   ```bash
   cd hush_tag

3. Install dependencies:
    ```bash
    npm install
4. Build the TypeScript code: 
    ```bash
    npm run build


##Usage
1. Start the server:
   ```bash
   node server.js

2. Open your browser and navigate to:

[http://localhost:4242](http://localhost:4242)  

3. From the UI, you can:
Generate a new ticket (creates a QR code).
Check/validate existing tickets by uploading the QR code image.
# Ticket System

## Overview
This project allows for the generation and validation of tickets using QR codes, powered by the Mina Protocol. The system utilizes smart contracts to track whether a ticket has been used or not, ensuring a secure and verifiable process.

## How It Works

### Ticket Generation
When a user clicks **"Generate Ticket"**:
1. A new Mina smart contract is created.
2. A smart contract is deployed to that account with an initial state of "unused."
3. A QR code containing the public key of the account is generated.
4. The QR code and the public key are displayed to the user.

### Ticket Validation
When a user clicks **"Check Ticket"** and uploads a QR code:
1. The system reads the public key from the QR code.
2. It checks the state of the smart contract at that address.
3. The system returns one of the following states:
   - **ACCEPTED**: A valid ticket that hasn't been used before (and marks it as used).
   - **HANDLED**: A valid ticket that has already been used.
   - **UNCOVERED**: An invalid ticket or QR code.

### Smart Contract
The core of the system is a simple smart contract called **Hush**, which stores a state indicating whether a ticket has been used or not. The contract's state changes as follows:
- `0` (unused): The ticket is valid but has not yet been used.
- `1` (used): The ticket has been used.

# Project Structure

- **src**: TypeScript source code for the blockchain logic  
- **frontend**: Web UI for the application  
- **img**: Generated QR codes  
- **uploads**: Temporary storage for ticket validation uploads  

## License  
This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.  

## Acknowledgements  
- Powered by [Mina Protocol](https://minaprotocol.com)  
- Built with [o1js](https://github.com/o1-labs/o1js)  
