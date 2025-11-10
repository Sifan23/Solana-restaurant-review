# 🍽️ Restaurant Review dApp — Built on Solana

A **decentralized application (dApp)** for creating, updating, and viewing restaurant reviews, powered by the **Solana blockchain**.
This project demonstrates how on-chain Solana programs integrate seamlessly with a **Next.js** front end for a modern Web3 experience.

---

## 🚀 Overview

The **Restaurant Review dApp** enables users to:

* 📝 **Add restaurant reviews** (title, description, and rating)
* ✏️ **Update their own reviews**
* 👀 **Browse all existing reviews** on-chain

### Architecture

The system consists of two main components:

#### 🧠 1. Solana Program (On-Chain Logic)

A **Rust-based Solana program** (smart contract) responsible for:

* Storing and managing reviews
* Enforcing ownership (only creators can update their reviews)
* Providing review data to the client

#### 💻 2. Front End (Off-Chain Web App)

A **Next.js** Single Page Application styled with **Tailwind CSS**, providing:

1. **Wallet Connection** — via the Solana Wallet Adapter (supports Phantom, Solflare, etc.)
2. **Review Submission Form** — for entering title, description, and rating
3. **Review Display Section** — showing all reviews retrieved from the Solana blockchain

---

## 🧩 Tech Stack

| Layer                       | Technology                                                             |
| --------------------------- | ---------------------------------------------------------------------- |
| **Blockchain**              | [Solana](https://solana.com/)                                          |
| **Smart Contract Language** | [Rust](https://www.rust-lang.org/)                                     |
| **Frontend Framework**      | [Next.js](https://nextjs.org/)                                         |
| **Styling**                 | [Tailwind CSS](https://tailwindcss.com/)                               |
| **Wallet Integration**      | [Solana Wallet Adapter](https://github.com/solana-labs/wallet-adapter) |
| **Blockchain Client**       | [@solana/web3.js](https://solana-labs.github.io/solana-web3.js/)       |
| **RPC Provider**            | Solana Devnet / Mainnet                                                |



---

## 🛠️ Setup & Installation

### Prerequisites

Ensure you have the following installed:

* [Rust & Cargo](https://www.rust-lang.org/tools/install)
* [Solana CLI](https://docs.solana.com/cli/install-solana-cli-tools)
* [Node.js](https://nodejs.org/) (v18+ recommended)
* [Yarn](https://yarnpkg.com/) or npm

---

### 1. Clone the Repository

```bash
git clone https://github.com/Sifan23/Solana-restaurant-review
cd Solana-restaurant-review
```

---

### 2. Build and Deploy the Solana Program

```bash
cd program
cargo build-bpf
solana program deploy ./target/deploy/restaurant_review.so
```

> 🧾 **Note:** Copy the **Program ID** printed after deployment.
> You’ll use it in your front-end `.env.local` file.

---

### 3. Configure the Front End

Create a `.env.local` file in the `/app` directory:

```bash
NEXT_PUBLIC_SOLANA_NETWORK=devnet
NEXT_PUBLIC_PROGRAM_ID=<YOUR_PROGRAM_ID>
```

---

### 4. Install Dependencies & Run the App

```bash
cd ../app
yarn install
yarn dev
```

Visit **[http://localhost:3000](http://localhost:3000)** to view the dApp.

---

## 💡 Usage

1. Open the dApp in your browser.
2. Connect your **Solana wallet** (Phantom, Solflare, etc.).
3. Submit a restaurant review using the form (title, description, rating).
4. Reviews will appear below the form, pulled directly from the blockchain.
5. You can edit your review if it was created by your connected wallet.

---

## 🔐 Security

* Reviews are stored **on-chain** and tied to the user’s **public key**.
* Only the original author can **update their review**.
* Review data is immutable and transparently viewable by anyone.

---

## 🧠 Future Improvements

* ⭐ **Sorting & Filtering:** Order reviews by rating or restaurant name.
* 🖼️ **Media Uploads:** Add support for restaurant images (via IPFS or Arweave).
* 📱 **Responsive Design Enhancements:** Improve UX on mobile devices.
* 🏆 **Reputation System:** Introduce trust scores for reviewers.

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for more details.

---

## 🤝 Contributing

Contributions, suggestions, and bug reports are welcome!
Please open an issue or submit a pull request.

---
