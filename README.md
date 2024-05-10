# Create-Tokens_In-Solana-Using-CLI

Install curl:
```bash
sudo apt  install curl  # version 7.88.1-8ubuntu2.3
```
Install Rust Programming Language:
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
Check installed or not:
```bash
rustc --version
```
Install Solana:
```bash
sh -c "$(curl -sSfL https://release.solana.com/v1.18.12/install)"
```
And importantly, update your PATH environment variable

Generate your Public Key and Key-pair path:
```bash
solana-keygen --new
```
Print your Public Key:
```bash
solana-keygen pubkey
```
Set your network to devnet(test network):
```bash
solana config set ---url https://api.devnet.solana.com
```
Check your account balance. It will be shown 0 Sol.
```bash
solana balance
```
Add value in your account:
```bash
solana airdrop 5 <Your_Generated_Public_key>
//You can run solana-keygen pubkey command to get your Public Key
```
Now you check the balance of your account is updated to 5 Sol.
Install spl:
```bash
cargo install spl-token-cli
```
Create token:
```bash
spl-token create-token
```
You will get a token address, store that address.
Create Account for that token:
```bash
spl-token create-account <Token_Address>
```
You will get a Recipent Address also, store that address.
Generate tokens:
```bash
spl-token mint <Token_Address> 100
```
Now, you can check the balance:
```bash
spl-token balance <Token_Address>
```


