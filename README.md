# Creating Tokens in Solana using CLI

## Overview
This README provides a step-by-step guide on how to create tokens on the Solana blockchain using the Command Line Interface (CLI). Solana offers a robust CLI toolset that simplifies the process of token creation and management.

## Steps
### 1.Install Rust Programming Language:
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
Check installed or not:
```bash
rustc --version
```
### 2.Install Solana:
```bash
sh -c "$(curl -sSfL https://release.solana.com/v1.18.12/install)"
```
⭐ Importantly, update your PATH environment variable

### 3.Generate your Public Key and Key-pair path:
```bash
solana-keygen --new
```
⭐ Make sure that the path of your key-pair shouldn't contain any spaces.
Print your Public Key:
```bash
solana-keygen pubkey
```
### 4.Set your network to Devnet(Test Network):
```bash
solana config set ---url https://api.devnet.solana.com
```
Check your account balance. 0 Sol will be displayed.
```bash
solana balance
```
### 5.Add value in your account:
```bash
solana airdrop 5 <Your_Generated_Public_key>
//You can run solana-keygen pubkey command to get your Public Key
```
Now you check the balance of your account is updated to 5 Sol.
### 6.Install spl:
```bash
cargo install spl-token-cli
```
### 7.Create token:
```bash
spl-token create-token
```
You will get a token address, store that address.
### 8.Create Account for that token:
```bash
spl-token create-account <Token_Address>
```
Please store the recipient address that you will receive.

### 9.Generate tokens:
```bash
spl-token mint <Token_Address> 100
```
Now, you can check the balance:
```bash
spl-token balance <Token_Address>
```
### 10.Disable further minting of the token:
```bash
spl-token authorize <Token_Address> mint --disable
```
### 11.Burn some amount of tokens:
```bash
spl-token burn <Recipient_Address> 10
```
Create an account in Phantom wallet and choose Devnet instead of the main network.
Copy the Phantom wallet address.
### 12.Transfer some tokens to the Phantom wallet:
```bash
spl-token transfer <Token_Address> 50 <Phantom_Wallet_Address>
```
## Additional Resources
For more information and advanced usage, refer to the Solana Documentation and SPL Token Program Documentation.

