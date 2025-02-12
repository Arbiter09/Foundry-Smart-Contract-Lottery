# 🎟️ Raffle Smart Contract - Chainlink VRF & Automation Integrated Lottery

## 📌 Overview

This project implements a **decentralized raffle system** using **Chainlink VRF v2.5** for **provable randomness** and **Chainlink Automation (Keepers)** to automate winner selection.

### Key Features:

- **Fair & Transparent Lottery**: Uses **Chainlink VRF** for random winner selection.
- **Automated Execution**: **Chainlink Keepers** automate winner selection & fund transfers.
- **Fully Tested**: **Unit & integration tests** ensure reliability.
- **Supports Multiple Networks**: Configurable for **local development & Sepolia testnet**.

---

## 📂 Project Structure

The following describes the **directory structure**:

```
.
├── .github/                     # GitHub actions (CI/CD)
├── broadcast/                   # Stores transaction execution traces
├── cache/                        # Cached build artifacts
├── lib/                          # External dependencies (installed via `forge install`)
├── out/                          # Compiled contract output
│
├── script/                       # Foundry scripts for deployment & interaction
│   ├── DeployRaffle.s.sol        # Deploys the Raffle contract
│   ├── HelperConfig.s.sol        # Manages blockchain configurations
│   ├── Interactions.s.sol        # Handles Chainlink VRF subscription, funding, and adding consumers
│
├── src/                          # Core Solidity contracts
│   ├── Raffle.sol                # The main Raffle smart contract
│
├── test/                         # Contains test files for the project
│   ├── integration/              # Integration tests
│   │   ├── Interactions.t.sol    # Tests for Chainlink VRF & Keepers
│   ├── mocks/                    # Mock contracts for testing
│   │   ├── LinkToken.t.sol       # Mock LINK token for VRF testing
│   ├── unit/                     # Unit tests
│   │   ├── RaffleTest.t.sol      # Unit tests for Raffle contract
│
├── .env                          # Stores environment variables (private keys, RPC URLs)
├── .gitignore                    # Git ignored files
├── .gitmodules                   # Git submodules
├── coverage.txt                   # Code coverage report
├── foundry.toml                   # Foundry configuration file
├── json.json                      # Configuration (if applicable)
├── Makefile                       # Automation for deployment, testing, and VRF interactions
├── README.md                      # Project documentation
```

---

## 🛠 Prerequisites

Before running the project, ensure you have:

- **[Foundry](https://book.getfoundry.sh/getting-started/installation)**
- **Node.js** (for optional additional tools)
- **Anvil** (local Ethereum testnet)
- **A Sepolia testnet wallet with ETH & LINK**

---

## 🚀 Setup & Installation

### 1️⃣ Clone the Repository

```sh
git clone https://github.com/Arbiter09/Foundry-Smart-Contract-Lottery.git
cd Foundry-Smart-Contract-Lottery
```

### 2️⃣ Install Dependencies

```sh
make install
```

This installs:

- **Foundry DevOps**
- **Chainlink Brownie Contracts**
- **Forge Standard Library**
- **Solmate Utilities**

### 3️⃣ Set Up Environment Variables

Create a `.env` file and add:

```ini
SEPOLIA_RPC_URL=YOUR_INFURA_OR_ALCHEMY_URL
PRIVATE_KEY=YOUR_WALLET_PRIVATE_KEY OR ELSE USE CAST WALLET (RECOMMENDED)
ETHERSCAN_API_KEY=YOUR_ETHERSCAN_API_KEY
```

---

## 💻 Running the Project

### 1️⃣ Start Local Blockchain

```sh
make anvil
```

This starts a **local Ethereum node** for testing.

### 2️⃣ Deploy Contracts

```sh
make deploy
```

Deploys the **Raffle contract** on the selected network.

### 3️⃣ Run Tests

```sh
make test
```

Runs **unit & integration tests**.

### 4️⃣ Take a Snapshot

```sh
make snapshot
```

Saves blockchain state for **quick testing**.

---

## 🔗 Chainlink VRF & Keepers Setup

### 1️⃣ Create a Chainlink VRF Subscription

```sh
make createSubscription
```

- Creates a **VRF subscription** for random number requests.

### 2️⃣ Fund Subscription

```sh
make fundSubscription
```

- Adds **3 LINK tokens** to the subscription.

### 3️⃣ Register Raffle as a Consumer

```sh
make addConsumer
```

- Registers the **Raffle contract** as a VRF consumer.

---

## 📜 Deployment on Sepolia Testnet

### Deploy & Verify

```sh
make deploy-sepolia
```

This:

1. **Deploys the contract on Sepolia**.
2. **Verifies it on Etherscan**.

---

## 🧪 Testing

### 1️⃣ Run All Tests

```sh
forge test --fork-url $SEPOLIA_RPC_URL -vvv
```

- Runs **all tests** with detailed logs.

### 2️⃣ Individual Test Files

```sh
forge test --match-test testCreateSubscriptionUsingConfig
```

- Runs a specific test case.

### 3️⃣ Generate Coverage Report

```sh
forge coverage
```

- Shows test **coverage percentage**.

---

## 📜 License

This project is **MIT licensed**. Feel free to use and modify it.

---

## 📌 Summary

✅ **Decentralized, fair lottery system**  
✅ **Automated execution with Chainlink Keepers**  
✅ **Uses Chainlink VRF for provable randomness**  
✅ **Fully tested & supports local/Sepolia deployments**

Enjoy building with this **provably fair, blockchain-based raffle system!** 🎉
