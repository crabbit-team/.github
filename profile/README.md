<p align="center">
  <img src="https://raw.githubusercontent.com/crabbit-team/frontend/main/public/logos/Tokki.png" alt="Tokki" width="120"/>
  <br>
  <img src="https://raw.githubusercontent.com/crabbit-team/frontend/main/public/logos/logo.png" alt="Crabbit Logo" width="280"/>
</p>

<div align="center">

*Share-based vault strategy investment for MemeCore ecosystem*

[![Built on MemeCore](https://img.shields.io/badge/Built%20on-MemeCore-orange)](https://memecore.com) [![Solidity](https://img.shields.io/badge/Solidity-0.8.24-blue)](https://soliditylang.org/) [![Tests](https://img.shields.io/badge/Tests-170%20Passing-green)](https://github.com/crabbit-team/contract)

</div>

- 🌐 **[Launch App](https://crabbitweb.vercel.app/)**
- 🏆 **[MemeCore Memekathon 2025](https://memekathon.memecore.com/ko)**

---

## 📦 Repositories

| Repository | Description |
|------------|-------------|
| [**contract**](https://github.com/crabbit-team/contract) | Smart contracts (Vault shares, Uniswap V3 integration) |
| [**backend**](https://github.com/crabbit-team/backend) | FastAPI backend (vault data, token prices) |
| [**frontend**](https://github.com/crabbit-team/frontend) | Next.js web app (vault UI, portfolio tracking) |

---

## 🎯 Problem & Solution

### The Problem
- **High Volatility**: Single meme coin investments carry extreme risk
- **Copy-Trading Slippage**: Followers lose money when leader trades execute first
- **Low Liquidity**: Shallow markets cause price manipulation and failed trades
- **Complex UX**: Managing multiple tokens requires advanced DeFi knowledge

### Our Solution
- ✅ **Tokenized Vault Shares**: All investors get identical NAV per share—eliminates front-running
- ✅ **Diversified Portfolios**: Reduce single-token risk through multi-asset vaults
- ✅ **USDC-Only Entry**: Single-token investment, no need to manage individual meme coins
- ✅ **TWAP Oracle Pricing**: Manipulation-resistant pricing via Uniswap V3 30-minute TWAP


---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                        Frontend (Next.js)                    │
│  ┌─────────────────┐  ┌──────────────────┐  ┌─────────────┐│
│  │   Vault List    │  │  Strategy Build  │  │ Leaderboard ││
│  │   & Details     │  │   (AI Assist)    │  │   & Tiers   ││
│  └─────────────────┘  └──────────────────┘  └─────────────┘│
└─────────────────────────────────────────────────────────────┘
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                    Backend API (FastAPI)                     │
│  ┌─────────────────┐  ┌──────────────────┐  ┌─────────────┐│
│  │  Vault Service  │  │  Token Service   │  │ Auth/Wallet ││
│  │  (TVL, APY)     │  │  (Price, Info)   │  │   Service   ││
│  └─────────────────┘  └──────────────────┘  └─────────────┘│
└─────────────────────────────────────────────────────────────┘
                              ▼
┌─────────────────────────────────────────────────────────────┐
│              Smart Contracts (MemeCore Testnet)              │
│  ┌──────────────────┐  ┌──────────────────┐  ┌────────────┐│
│  │ MemeVaultFactory │  │   MemeVault      │  │ CrtToken   ││
│  │ (ERC-4626)       │  │   (Proxy)        │  │ (Utility)  ││
│  └──────────────────┘  └──────────────────┘  └────────────┘│
│  ┌──────────────────┐  ┌──────────────────┐  ┌────────────┐│
│  │ UniswapV3Oracle  │  │  VaultManagerNFT │  │FeeCollector││
│  │ (TWAP Pricing)   │  │  (Ownership)     │  │            ││
│  └──────────────────┘  └──────────────────┘  └────────────┘│
└─────────────────────────────────────────────────────────────┘
                              ▼
                    🌐 MemeCore Blockchain
              (Uniswap V3, Meme Tokens, USDC)
```

---

## 🔧 Technical Implementation

### Smart Contracts (Solidity 0.8.24)
**Repository**: [contract](https://github.com/crabbit-team/contract)

**Deployed Features:**
- ✅ Vault share token implementation with minimal proxy pattern
- ✅ MemeVaultFactory for vault deployment
- ✅ UniswapV3TWAPOracle (30-minute TWAP)
- ✅ VaultManagerNFT (ownership management)
- ✅ CrtToken (500 CRT vault creation fee)
- ✅ FeeCollector (70% burn, 30% treasury)
- ✅ RewardDistributor with signature-based claims
- ✅ 170 passing tests (100% core functionality coverage)

**Tech Stack:** Foundry, OpenZeppelin 5.1.0, Uniswap V3

### Backend API (Python 3.11+)
**Repository**: [backend](https://github.com/crabbit-team/backend)

**Implemented Features:**
- ✅ Vault TVL and NAV calculation (decimal-adjusted)
- ✅ Token price aggregation from on-chain sources
- ✅ RESTful API with FastAPI auto-docs
- ✅ Web3.py integration with MemeCore RPC
- ✅ Real-time share price updates

**Tech Stack:** FastAPI, Web3.py, Pydantic, Uvicorn

### Frontend (Next.js 14)
**Repository**: [frontend](https://github.com/crabbit-team/frontend)

**Features:**
- Vault discovery and filtering UI
- Investment flow (USDC → Vault shares)
- Portfolio tracking dashboard
- wagmi/viem wallet integration

**Tech Stack:** Next.js 14, TypeScript, TailwindCSS, wagmi

---

## 🌟 Live Deployment

- **Network**: MemeCore Insectarium Testnet
- **Chain ID**: 43522
- **RPC**: https://rpc.insectarium.memecore.net
- **Explorer**: https://insectarium.blockscout.memecore.com

## 📚 Documentation

- [Contract Documentation](https://github.com/crabbit-team/contract#readme) - Solidity contracts, deployment, testing
- [API Documentation](https://github.com/crabbit-team/backend#readme) - Backend API endpoints, data models
- [Frontend Guide](https://github.com/crabbit-team/frontend#readme) - UI components, wallet integration

---

<div align="center">

**Built for MemeCore Memekathon 2025**

*On-chain meme coin ETF platform powered by tokenized vault shares*

[Contract](https://github.com/crabbit-team/contract) • [Backend](https://github.com/crabbit-team/backend) • [Frontend](https://github.com/crabbit-team/frontend)

</div>
