# 🦀 Crabbit

> **Social Trading Meets Meme ETF Strategy**
> Invest in curated meme coin portfolios managed by AI and human strategists on MemeCore

[![MemeCore](https://img.shields.io/badge/Built%20on-MemeCore-orange)](https://memecore.com)
[![Solidity](https://img.shields.io/badge/Solidity-0.8.24-blue)](https://soliditylang.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 🎯 What is Crabbit?

Crabbit is a **gamified on-chain ETF platform** for meme coins built exclusively on MemeCore. Unlike traditional copy-trading where followers suffer from slippage and front-running, Crabbit uses **ERC-4626 vault shares** to ensure all investors get the same price regardless of when they enter.

### The Problem We Solve

- **High Volatility**: Single meme coin bets are extremely risky
- **Low Liquidity**: Most meme tokens have shallow markets causing price manipulation
- **Information Asymmetry**: Twitter calls and Telegram signals are unverifiable and often scams
- **Copy-Trading Failures**: Followers lose money due to slippage while leaders profit first
- **Complex UX**: Managing wallets, gas, swaps, and bridges is too difficult for newcomers

### Our Solution

✅ **ETF-Style Vaults**: Diversified meme coin portfolios reduce single-token risk
✅ **Share-Based Investment**: All investors get the same NAV per share—no front-running
✅ **AI Strategy Assistant**: Anyone can create professional-grade portfolios with AI help
✅ **Social Leaderboard**: Transparent performance tracking with reputation system
✅ **One-Click Investment**: Buy vault shares with USDC only—no need to manage individual tokens

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

## 📦 Repositories

### 🔧 [contract](https://github.com/crabbit-team/contract)
Smart contracts powering the vault system

**Key Features:**
- ERC-4626 compliant vault implementation
- Uniswap V3 TWAP price oracle integration
- Manager NFT for vault ownership
- CRT token utility and fee collection
- Comprehensive test suite (170 tests)

**Tech Stack:** Solidity 0.8.24, Foundry, OpenZeppelin

### 🖥️ [backend](https://github.com/crabbit-team/backend)
FastAPI backend serving vault data and token information

**Key Features:**
- Real-time vault TVL and share price calculation
- Token price aggregation from on-chain sources
- RESTful API with automatic documentation
- Decimal-adjusted responses for frontend consumption

**Tech Stack:** Python 3.11+, FastAPI, Web3.py, Pydantic

### 🎨 [frontend](https://github.com/crabbit-team/frontend)
Next.js web application for investors and managers

**Key Features:**
- Vault discovery and investment interface
- AI-assisted strategy creation
- Real-time portfolio tracking
- Responsive design for mobile and desktop

**Tech Stack:** Next.js 14, TypeScript, TailwindCSS, wagmi/viem

---

## 🚀 Quick Start

### For Investors

1. **Connect Wallet** → MetaMask or WalletConnect
2. **Browse Vaults** → Filter by performance, risk, or strategy type
3. **Invest USDC** → One-click purchase of vault shares
4. **Track Portfolio** → Monitor NAV and performance in real-time

### For Managers

1. **Create Strategy** → Use AI assistant or manual configuration
2. **Deploy Vault** → Factory creates your ERC-4626 vault
3. **Add Liquidity** → Initialize with meme coin positions
4. **Earn Fees** → 2% management fee + 20% performance fee

---

## 🌟 Live Deployment

**Network**: MemeCore Insectarium Testnet
**Chain ID**: 43522
**RPC**: https://rpc.insectarium.memecore.net
**Explorer**: https://insectarium.blockscout.memecore.com

### Core Contracts

| Contract | Address | Explorer |
|----------|---------|----------|
| MemeVaultFactory | `0xC83C2F3D8DB882dF24ACC770978C66c95FAcDa25` | [View](https://insectarium.blockscout.memecore.com/address/0xc83c2f3d8db882df24acc770978c66c95facda25) |
| UniswapV3TWAPOracle | `0xAD6acF19b5eEd4580C9513a8F4A9DC86A1E66c40` | [View](https://insectarium.blockscout.memecore.com/address/0xad6acf19b5eed4580c9513a8f4a9dc86a1e66c40) |
| CrtToken | `0x8371e24Ad7252f4BE6dE1AE7F589Fd82A4bcb940` | [View](https://insectarium.blockscout.memecore.com/address/0x8371e24ad7252f4be6de1ae7f589fd82a4bcb940) |

*See individual repositories for full deployment details*

---

## 🎮 Gamification Features

### 🏆 Vault Tiers
- **Diamond** (Top 5%): Best performing vaults
- **Platinum** (Top 10%): Excellent track record
- **Gold** (Top 25%): Solid performance
- **Silver** (Top 50%): Decent returns
- **Bronze** (Top 75%): Entry level
- **Iron** (All others): New or underperforming

### 📊 Leaderboard Metrics
- Total Value Locked (TVL)
- 7-day / 30-day / All-time Returns
- Sharpe Ratio & Max Drawdown
- Active Investor Count

### 🎯 Battle Mode (Future)
- Compete against AI strategies
- Seasonal rankings and rewards
- Strategy duplication and evolution

---

## 🔐 Security

✅ **Audited Contracts**: Core logic reviewed and tested
✅ **Non-Custodial**: Users maintain full control of funds
✅ **TWAP Oracle**: Manipulation-resistant pricing
✅ **Manager Reputation**: On-chain track record prevents rug pulls
✅ **Slippage Protection**: Swap limits and minimum output checks

---

## 📚 Documentation

- [Contract Documentation](https://github.com/crabbit-team/contract#readme)
- [API Documentation](https://github.com/crabbit-team/backend#readme)
- [Frontend Guide](https://github.com/crabbit-team/frontend#readme)

---

## 🤝 Contributing

We welcome contributions! Please see individual repository CONTRIBUTING.md files for guidelines.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'feat: add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📞 Contact & Community

- **Twitter**: [@CrabbitFi](https://twitter.com/CrabbitFi) *(example)*
- **Discord**: [Join our server](https://discord.gg/crabbit) *(example)*
- **Email**: hello@crabbit.fi *(example)*

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

<div align="center">

**Built with 🦀 for MemeCore Memekathon 2024**

*Democratizing meme coin investing through ETF strategies and social trading*

</div>
