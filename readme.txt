# 🧠 DeFi Wallet Credit Scoring using Aave V2 Data

## 📌 Overview

This project generates **credit scores (0–1000)** for Ethereum wallets using **DeFi transaction data** from the **Aave V2 protocol**. By analyzing borrowing, repaying, and liquidation behavior, it offers a way to evaluate the financial trustworthiness of wallets in the decentralized ecosystem.

---

## 📊 Goal

Create a transparent, behavior-based credit scoring system that helps DeFi protocols or users assess wallet credibility without traditional credit history.

---

## 📁 Files in This Project

| File Name                    | Description                                       |
|-----------------------------|---------------------------------------------------|
| `wallet_credit_score.ipynb` | Main Jupyter Notebook with code and logic        |
| `wallet_scores.csv`         | Final output: wallet addresses and credit scores |
| `README.md`                 | This documentation file                          |

---

## 🗂 Dataset Info

- **Source**: Aave V2 Protocol
- **Records**: 100,000+ transactions
- **Fields**: Wallet Address, Transaction Type (Borrow/Repay/Liquidation), Token, Amount, Timestamp

> 📝 Note: The full dataset is not uploaded due to size limits. You may use a sample or request access.

---

## ⚙️ Features Used for Scoring

- Total borrows and repays
- Repayment ratio
- Total volume borrowed/repaid
- Liquidation count
- Activity duration (days active)
- Normalized and weighted to calculate credit scores

---

## 🧠 Credit Score Logic (Simplified)

```python
wallet_features['credit_score'] = (
    wallet_features['repay_ratio'] * 0.4 +
    wallet_features['borrow_volume_norm'] * 0.3 +
    wallet_features['liquidation_score'] * 0.3
) * 1000
