# Krank Lottery: A Solana-Based Web3 Lottery System 🎟️

## [Visuals]()

**Revolutionizing Virtual Casinos with Decentralized Lotteries**



## Whats Krank😎🏨?
Krank is a cutting-edge Web3 virtual casino project built on the Solana blockchain.
It leverages blockchain technology to provide transparency, fairness, and decentralization in gaming. 
Krank offers a variety of games, with the Krank Lottery Contract being one of its flagship features.

## Overview of the Krank Lottery Contract💰🎟️
A Solana-based smart contract developed using the Anchor framework.
Powers a decentralized lottery system where users can buy tickets and win prizes💰.
Lottery sessions run every two weeks, ensuring regular engagement and excitement. This system operates on three key features: 
**Transparency**, **Fairness**, **Decentralization**.
#### **Transparency:** 
All transactions and outcomes are recorded on the Solana blockchain ensuring public transparency.
#### **Fairness:**
Winners are selected using a provably fair time ⏲️ functional random undeterministic algorithm.
#### **Decentralization:**
No central authority controls the lottery sessions. It is strictly time based and can only be closed when the time elapses.

## [Visuals]()

## How Krank Lottery Contract Works⛓️⚙️

### [Visuals]()

### 📌 Developer/Owner Functions
These functions can only be executed by the contract owner or developer to set up and manage the lottery system.

**1️⃣ initialize_lottery_vault**
**🔹 Purpose:** Creates a permanent vault address to securely store all SOL (Solana tokens) received by the contract. This vault is used for managing lottery funds.

**🔹 Why is this important?**

Ensures that lottery funds are stored safely.
Prevents unauthorized withdrawals.

**2️⃣ initialize_lottery_counter**
**🔹 Purpose:** Sets up a counter to keep track of all lottery sessions. Every new lottery session gets a unique identifier, preventing confusion between different lotteries.

**🔹 Why is this important?**

Ensures that no two lottery sessions have the same ID.
Helps in tracking lottery history efficiently.

**3️⃣ create_lottery**
**🔹 Purpose:** Allows the owner to create a new lottery session, specifying the ticket price for participation.

**🔹 Why is this important?**

Enables the contract to run multiple lottery sessions.
Allows the owner to set custom ticket prices.

**4️⃣ declare_winner**
**🔹 Purpose:** Randomly selects a winning ticket for a given lottery session.

**🔹 Parameters:**

**lottery_id:** The unique ID of the lottery session.

**🔹 Why is this important?**

### 👥 User Functions
These functions can be used by anyone who wants to participate in the lottery.

**5️⃣ buy_ticket**
**🔹 Purpose:** Allows users to buy a lottery ticket for a specific lottery session.

**🔹 Parameters:**

**lottery_id:** Specifies which lottery session the ticket is for.

**🔹 Why is this important?**
Users can participate in the lottery fairly.
The contract keeps track of purchased tickets.

**6️⃣ claim_prize**
**🔹 Purpose:** If a user wins a lottery, they can claim their prize using this function.

**🔹 Parameters:**

**lottery_id:** The unique ID of the lottery session they won.

**🔹 Why is this important?**

Ensures that winners get their prizes securely.
Prevents unauthorized claims by verifying the winner’s ticket.
Ensures fairness by randomly selecting a winner.
Helps automate the prize distribution process.



### How The Time⌚ Based Randomness Algorithm Works ⚙️
**Lottery Contract Randomness**
The lottery contract generates randomness using three numerical factors:

**1. Unix Timestamp:**
This timestamp represents the current time when the winner declaration function is executed in the contract.
Since it continuously changes, it introduces unpredictability.

**2. Epoch Number:**
The epoch number is time-dependent and fluctuates slightly by ±1.
It typically lasts for 432,000 slots and is obtained using the ```Clock::get()``` method.

**3. Slot Digit:**
A constant value of ```432,000```, retrieved from the Clock::get() function, representing a predefined time interval.

**Generation of Randomness**
The randomness is derived from a combination of the current Unix timestamp, the current epoch, and the constant slot value. This approach enhances unpredictability and reduces the likelihood of manipulation.
Randomness in Winner Selection
The winner is determined using the Modulo operation:
```Randomness % total tickets bought = winning ticket number```


Since the total number of tickets purchased in a slot varies dynamically, it further enhances unpredictability, making it difficult to predetermine the winner.

### 🛠️ How It Works
The owner sets up the lottery system by initializing the vault and lottery counter.
A new lottery session is created with a defined ticket price.
Users buy tickets using SOL.
When the lottery ends, the owner declares a winner randomly.
The winner claims their prize, which is securely transferred from the vault.

### 🔐 Security Measures
**✅ Fair Randomness:** Uses a secure and unpredictable method to determine winners.

**✅ Vault Protection:** Funds are stored securely in the contract.

**✅ Unique Lottery Sessions:** Prevents mix-ups between different lotteries.

**✅ Transparent Transactions:** Everything is recorded on the blockchain.




