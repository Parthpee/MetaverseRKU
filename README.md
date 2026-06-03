

[FINAL_REPORT](https://github.com/Parth123-Pro/MetaverseRKU/files/10050047/FINAL_REPORT_.pdf)

# MetaverseRKU: Decentralized Canvas Metaverse

A high-performance, web-based 2D metaverse ecosystem built with an event-driven Web3 architecture. This project bridges an interactive HTML5 graphic landscape with an on-chain ERC-721 smart contract layer, using low-latency data streams to reflect true asset ownership in real-time.[cite: 1]
<img width="790" alt="Screenshot 2022-10-04 at 10 51 24 AM" src="https://user-images.githubusercontent.com/55745745/193741058-8fbd1143-4443-4b91-9aa4-bff4515c34d8.png">

---

## 🏗️ System Architecture

The application bypasses slow, traditional JSON-RPC polling loops by leveraging a reactive Web3 indexer and stream workflow:[cite: 1]



<img width="454" height="379" alt="Screenshot 2026-06-03 at 12 27 26" src="https://github.com/user-attachments/assets/ba16dd52-1b60-4b7f-9a9c-6cf592ffc7ec" />



### Key Highlights
* **On-Chain Identity:** Every individual coordinate land grid plot is hashed cryptographically and linked to a unique ERC-721 Token ID.[cite: 1]
* **Reactive Map States:** Real-time event streams listen for on-chain `Transfer` emissions, modifying UI canvas tiles instantly via webhooks without page reloads.[cite: 1]
* **Hybrid Storage Pattern:** Keeps execution costs at a minimum by utilizing gas-efficient testnets combined with metadata pointer mappings.[cite: 1]

---

## 🚀 Key Features & User Walkthrough

### 1. Web3 Authentication
Users authenticate by connecting their decentralized wallets (e.g., MetaMask). The frontend reads the active wallet address to verify existing plot ownership balances across the grid.[cite: 1]

### 2. Interactive Coordinate Selection
The main stage runs on an HTML5 canvas layer rendering custom tile patterns. Moving the cursor over the map tracks local grid matrix coordinates (`plotX`, `plotY`), which automatically converts the coordinates into a single cryptographic hash mapping ID.[cite: 1]

### 3. Verification & Live Indexing Status
When a tile is clicked, the app sends a low-latency request using a Web3 Data Indexing API layer to inspect if the land parcel's `TokenID` hash exists on-chain.[cite: 1]
* **Available Plots:** Unlocked for purchase with an active "Mint Land" execution view.[cite: 1]
* **Claimed Plots:** Styled dynamically as occupied, rendering the owner’s compressed wallet identity.[cite: 1]

### 4. Smart Contract Minting & Stream Sync
Clicking "Mint Land" triggers an EVM transaction via Ethers.js. Once confirmed on-chain, a registered Web3 Stream webhook intercepts the execution log and fires an update directly back to the front-end map instance, locking the tile color in place instantly for all active users.[cite: 1]

---

## 🚀 Technical Stack

* **Frontend:** HTML5 Canvas, JavaScript (ES6+), Ethers.js, CSS3[cite: 1]
* **Smart Contracts:** Solidity, OpenZeppelin ERC-721 standard, Remix/Hardhat[cite: 1]
* **Web3 Infrastructure:** Web3 Data Indexing APIs, Webhook Event Streams[cite: 1]
* **Development Network:** EVM-compatible Testnets (Polygon Amoy / Base)[cite: 1]

---

## 🔧 Installation & Local Setup

### Prerequisites
* A Web3 browser wallet (e.g., MetaMask) configured with testnet funds.[cite: 1]
* Node.js (v18+ recommended).[cite: 1]
* Access tokens or API keys for your chosen Web3 indexing layer.[cite: 1]

### 1. Repository Initialization
```bash
git clone [https://github.com/YOUR_USERNAME/your-metaverse-repo.git](https://github.com/YOUR_USERNAME/your-metaverse-repo.git)
cd your-metaverse-repo

```

### 2. Configure Environment Variables

Create a `.env` file in your root backend or configuration directory:

```env
WEB3_API_KEY="your_api_key_here"
WEB3_STREAM_SECRET="your_webhook_validation_secret"
CONTRACT_ADDRESS="0x..."

```

### 3. Deploying the Smart Contract

1. Open the contract file located in `/contracts/LandContract.sol` inside your development suite (or Remix IDE).


2. Compile using compiler version **0.8.20** or higher.


3. Deploy to your target testnet and paste the resulting deployment hash/address into your client configuration files and your `.env` layout.



### 4. Running the Application

Launch your local web server environment to serve the client layout:

```bash
# Example using a fast local live-server extension or node environment
npm install
npm start

```

Navigate to `http://localhost:3000` inside your Web3-enabled browser.
<img width="670" alt="Screenshot 2024-07-12 at 19 16 54" src="https://github.com/user-attachments/assets/309c6deb-7d48-4d2c-81fb-c6d649900099">
<img width="720" alt="Screenshot 2024-07-12 at 19 17 03" src="https://github.com/user-attachments/assets/55d7b8b3-3677-4c00-b01b-66ed39524972">
<img width="690" alt="Screenshot 2024-07-12 at 19 17 13" src="https://github.com/user-attachments/assets/1f820bcc-420e-436e-bec8-faf36bd940be">
<img width="733" alt="Screenshot 2024-07-12 at 19 17 24" src="https://github.com/user-attachments/assets/b9f8187b-9693-4e11-97c3-22a1075ed2c9">
<img width="720" alt="Screenshot 2024-07-12 at 19 17 30" src="https://github.com/user-attachments/assets/3ea9057d-c4e5-436f-8a16-304631c4b91d">
<img width="750" alt="Screenshot 2024-07-12 at 19 17 38" src="https://github.com/user-attachments/assets/6cf32f26-b154-43fe-83e6-157e81b42477">
<hr>

---

## 💻 Core Logic Implementation

The frontend app tracks mouse-coordinates over the map layout matrix, generating deterministic `bytes32` strings that link direct UI canvas interactions to specific smart contract storage locations.

```javascript
// Map viewer controller engine
function setPlotData() {
    // Cryptographically hash the unique tile coordinate matrix 
    const plotID = errors.utils.id(JSON.stringify(plotView));
    
    // Bind current coordinate transformations directly to structural UI inputs
    document.getElementById("plotX").value = plotView.plotX;
    document.getElementById("plotY").value = plotView.plotY;
    
    // Assign the unique hash identifier to handle upcoming Web3 mint operations
    document.getElementById("currentPlotId").value = plotID;
    
    // Execute low-latency indexing check to see if token ID is already claimed
    checkPlotOwnershipOnChain(plotID);
}

```
