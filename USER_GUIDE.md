# 📎 MetaPayP2P User Guide (Hyperion Testnet Edition)

## 📌 Overview
MetaPayP2P is a blockchain-based basic income simulation platform, running on the **Hyperion Testnet**.  
It visually demonstrates the flow of **MetaPay** and **cash** between individuals and companies, based on a **circulating basic income model**.  
It also integrates **AI-powered analysis** to detect economic patterns, distribution/recollection flows, and transaction behaviors.

> 🔟 **July 2025 Update**:  
> - All national → individual/company distributions are now included in AI analysis.  
> - AI analysis results appear instantly in the “AI Analysis Alerts” box (top-right).  
> - Hyperion Testnet deployment unified — no Sepolia or Mainnet usage.  

---

## 🔧 Key Features

### 🟢 Distribute (국가 → 개인/회사 분배)
- The national wallet distributes **MetaPay** and **cash** simultaneously to all user wallets.
- **Simulation Rule**:  
  - Perform **10 consecutive distributions**, then **1 recollection**, and repeat this cycle.
- These distribution records are included in AI analysis.

### 🔴 Collect (회수)
- Automatically recollects **10% of MetaPay** from all individual and company wallets back to the national wallet.

### ♻️ Reset (초기화)
- Resets all balances:  
  - National wallet → 50000  
  - All others → 0  

### 🧠 AI Analysis (AI 분석)
- Based on **wallet balances** and **transaction history**, AI detects:
  - Balance gaps between users
  - Company wallet activity patterns
  - Distribution flow impact
  - P2P transaction relationships
  - Imbalances in MetaPay supply
  - Failed or zero-value transactions
- **Result Display**: Appears in the top-right “AI Analysis Alerts” box instantly after pressing the button.

### ↺ Check Balances
- Displays **real-time** balances for national, individual, and company wallets.

### 📦 P2P Transfers (개인 간 거래)
- Clicking a **user box** auto-fills their wallet address into the “Recipient” field.
- **Always Available**:  
  - P2P transfers can be made **anytime**, independent of the 10-distribution cycle.  
  - "Send MetaPay + Cash" and "Send Cash Only" options are both supported.
- Cash transfers are controlled **entirely on the frontend**, allowing unrestricted frequency.

---

## 🧠 AI Analysis Example Output
```
- User1 has a lower balance due to multiple outgoing transactions.
- Company1 is highly active; Company3 and 4 show no recent activity.
- Users hold 91.3% of MetaPay supply; companies hold 8.7%.
- Several transactions were cash-only, likely test or special-purpose.
- National wallet performed 10 consecutive distributions before recollection.
```

---

## 🛠 System Requirements
- **MetaMask** wallet connection (Hyperion Testnet configured)
- Works on **Vercel** or local development environments
- **OpenAI API Key** required for AI functions

```bash
# .env file in project root:
OPENAI_API_KEY=sk-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```
> AI functions will not work without a valid key.

---

## 🚀 Usage Steps

### 1. Environment Setup
1. Create an account on [OpenAI](https://platform.openai.com/signup)
2. Copy your API key and store it in `.env` file.

### 2. Running Locally
```bash
# AI server
cd ai-server
node server.js

# Frontend
npm run dev
```

### 3. Simulation Flow
1. Press **Distribute** → repeat 10 times.
2. Press **Collect** once.
3. Repeat the above cycle for realistic simulation.
4. At any time, perform **P2P or cash-only transfers**.
5. Use **AI Analysis** to see flow insights instantly.

---

## 🧪 Architecture Overview

| Layer         | Technology                          |
|---------------|--------------------------------------|
| Smart Contract| Solidity (Hyperion Testnet)         |
| Frontend      | React (Vite)                        |
| Backend       | Node.js + Express                   |
| AI Integration| OpenAI API / analyze.js             |
| Wallet        | MetaMask                            |

**Project Structure**
```text
vite-project/
├── src/
│   ├── App.jsx              # Frontend logic
│   ├── abi.js               # ABI + contract address
├── ai-server/
│   ├── server.js            # AI API handler
│   ├── analyze.js           # AI analysis logic
├── contracts/
│   ├── MetaPayP2P_Complete.sol
├── public/
│   ├── metapay_full_flow_chart.png
```

---

## 🔗 Links & Resources
- GitHub: [MetaPayP2P Repo](https://github.com/metapay-creator/MetaPayP2P-Clean)  
- Simulation App (Vercel, Hyperion Testnet): [Launch App](https://meta-pay-p2-p-clean-7aig.vercel.app)  
- Contact: **anioia33@gmail.com**

---

© 2025 Gyuha Yoon. Licensed under MIT.  
Commercial use prohibited without permission.
