# Aegis Vault

Aegis is a simple and secure **token vault system** built on the **Solana Devnet**. Named after Aegis, the legendary shield of Zeus, it’s designed to safely hold minted tokens (in this case **DRT**) while tracking progress toward a target amount. Aegis makes it easy to **deposit**, **store**, and **monitor tokens** in one place — offering a clear, reliable way to manage on-chain assets during tests, experiments, or early-stage projects.

## Tokens Locked Screenshot and Hash

![Token Info](./docs/drt-vault.png)
_Screenshot showing the vault accounts with DRT tokens securely locked inside._

**Token Hash:** [`Fdw8FEek786AZhg4PSSm7nsgHCCu3MsorVhXgMeWZY9a`](https://explorer.solana.com/address/Fdw8FEek786AZhg4PSSm7nsgHCCu3MsorVhXgMeWZY9a?cluster=devnet)

> **Tokens Deposit Transaction Hash**:  
> `3NUKhXJggfJf8UyFwDkKNNWqjzZsbHYd5LxC1ABKM8d78vaa5t3KfXXadpgT1gNrjLsa7okF48vvmEw9LZcNNK7e`

[View Vault Token Account on Solana Explorer](https://explorer.solana.com/address/BhHxBocFdsRPuPZ4NRY8VW6xFDvE6825T4wHgwEAFUew?cluster=devnet)

## Signatures

- **Deployment:** [`2SpHtPZZpX9HytKvnNuMzPxRQFLFiFpB2pLaH5Hz4CunKLqcufg7vS917AxYKapYBM73SVbNZb8C1MmP1uj3zj4o`](https://explorer.solana.com/tx/2SpHtPZZpX9HytKvnNuMzPxRQFLFiFpB2pLaH5Hz4CunKLqcufg7vS917AxYKapYBM73SVbNZb8C1MmP1uj3zj4o?cluster=devnet)
- **Vault Init:** [`56k8YgtbEG51Smy74DN6mEdvXqa7sXEsyT8K2ZeaYHDiBZ2a1dzwuqKqUE85KF9uhX1tmPBzc7aNtZbTicQMvKiH`](https://explorer.solana.com/tx/56k8YgtbEG51Smy74DN6mEdvXqa7sXEsyT8K2ZeaYHDiBZ2a1dzwuqKqUE85KF9uhX1tmPBzc7aNtZbTicQMvKiH?cluster=devnet)
- **Tokens Deposit:** [`3NUKhXJggfJf8UyFwDkKNNWqjzZsbHYd5LxC1ABKM8d78vaa5t3KfXXadpgT1gNrjLsa7okF48vvmEw9LZcNNK7e`](https://explorer.solana.com/tx/3NUKhXJggfJf8UyFwDkKNNWqjzZsbHYd5LxC1ABKM8d78vaa5t3KfXXadpgT1gNrjLsa7okF48vvmEw9LZcNNK7e?cluster=devnet)

## Setup and Usage

1. Clone and install dependencies:

```bash
git clone https://github.com/devwraithe/aegis.git
cd aegis
yarn install
```

2. Run the escrow program:

```bash
yarn execute
```

## Tests

```bash
anchor test
```

## Deployment

Ensure your environment is configured for Devnet in Anchor.toml:

```toml
[programs.devnet]
themis = "<YOUR_PROGRAM_ID>"

[provider]
cluster = "devnet"
wallet = "~/.config/solana/id.json"
```

> [!IMPORTANT]
> Ensure your local or devnet wallet is funded (via airdrop or manual transfer) before running any transactions.

Set Solana CLI to devnet and deploy the program:

```bash
solana config set --url devnet
anchor deploy
```

> [!CAUTION]
**Note:** Minting requires the `mint_authority.json` file which is not included in the repository. Running the command above will auto-create a `user_keypair.json` file for you.

## Security

> [!IMPORTANT]
> **Never commit your `mint_authority.json` and `user_keypair.json` files or share their private keys.**

---

_In cryptography we trust, in Aegis we protect._
