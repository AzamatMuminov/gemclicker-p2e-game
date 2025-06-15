# Gem Clicker - A Play-to-Earn (P2E) Game Simulation

Welcome to Gem Clicker! This is a simple yet engaging Play-to-Earn (P2E) clicker game built with HTML, Tailwind CSS, and Firebase. This project serves as a fun, educational demonstration of Web 3.0 game mechanics in a simulated environment, without requiring actual blockchain transactions or cryptocurrency.

Users can "connect a wallet," earn in-game tokens by clicking, and then claim unique NFT rewards.

![image](https://user-images.githubusercontent.com/12423376/160447321-3c7d611b-3f04-4861-8938-04f7a2ab5363.png)
*(Feel free to replace this with a screenshot of your running application!)*

## ✨ Features

* **Click-to-Earn:** Simple and intuitive gameplay loop where clicks generate in-game tokens.
* **NFT Rewards:** Spend your earned tokens to claim unique, persistent NFT rewards.
* **Simulated Wallet:** "Connect Wallet" functionality is simulated using Firebase Anonymous Authentication to give each user a unique, persistent identity.
* **Persistent Data:** User token balances and claimed NFTs are saved to a Firebase Firestore database, so progress is never lost.
* **Real-time Updates:** Game state and NFT galleries update in real-time.
* **Standalone & Portable:** The entire application is contained within a single `index.html` file, making it easy to run anywhere.

## 🛠️ Technologies Used

* **Frontend:** HTML5, Tailwind CSS
* **Logic:** JavaScript (ES Modules)
* **Backend & Database:** Google Firebase
    * **Firebase Authentication:** To simulate unique user wallets.
    * **Firebase Firestore:** To store user data, token balances, and claimed NFTs.

## 🚀 Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites

You need a modern web browser (like Chrome, Firefox, or Edge).

### Installation & Setup

1.  **Clone the repo**
    ```sh
    git clone [https://github.com/AzamatMuminov/gemclicker-p2e-game.git](https://github.com/AzamatMuminov/gemclicker-p2e-game.git)
    cd gemclicker-p2e-game
    ```

2.  **Create a Firebase Project**
    * Go to the [Firebase Console](https://console.firebase.google.com/) and click **"Add project"**.
    * Give your project a name (e.g., "gem-clicker-p2e") and follow the on-screen instructions.

3.  **Register a Web App**
    * In your new project's dashboard, click the web icon (`</>`) to add a Firebase app to your project.
    * Give your app a nickname (e.g., "Gem Clicker Web") and click **"Register app"**.
    * Firebase will provide you with a `firebaseConfig` object. **Copy this object.** You'll need it in a moment.

4.  **Configure Firebase Services**
    * In the Firebase console, go to the **Build** section in the left-hand menu.
    * **Authentication:** Click on **Authentication**, then the **"Sign-in method"** tab. Enable the **"Anonymous"** sign-in provider.
    * **Firestore Database:** Click on **Firestore Database**, then **"Create database"**.
        * Start in **Test mode**. This will allow open read/write access while you are developing.
        * **Important:** For a real application, you would need to configure security rules to be more restrictive.
        * Choose a location for your database.

5.  **Add Your Firebase Config to the Project**
    * Open the `index.html` (or the main HTML file) in your code editor.
    * Find the `firebaseConfig` constant in the `<script type="module">` section.
    * **Paste the configuration object** you copied in Step 3, replacing the placeholder values.

    ```javascript
    // --- ⬇️ IMPORTANT: Firebase Configuration ⬇️ ---
    const firebaseConfig = {
        apiKey: "AIzaSy...YOUR_KEY", // Paste your config here
        authDomain: "your-project-id.firebaseapp.com",
        projectId: "your-project-id",
        storageBucket: "your-project-id.appspot.com",
        messagingSenderId: "1234567890",
        appId: "1:1234567890:web:abcdef123456"
    };
    // --- ⬆️ IMPORTANT: Firebase Configuration ⬆️ ---
    ```

6.  **Run the Game!**
    * That's it! Open the `index.html` file directly in your web browser. The game should now be running and connected to **your** Firebase backend.

## 💡 How the Web3 Simulation Works

This project mimics core Web3 concepts using Firebase as a stand-in for a real blockchain:

* **Wallet Address (`userId`)**: When a user "Connects Wallet," Firebase Authentication provides a unique, anonymous `userId`. This ID acts as the user's public wallet address to identify them and their assets.
* **On-Chain Data (Firestore)**: The Firestore database acts as the blockchain ledger. It stores all persistent data, such as how many tokens a user has and which NFTs they own.
* **Minting NFTs (Writing to Database)**: When a user "claims" an NFT, the application writes a new document to their collection in Firestore. This is analogous to a smart contract minting a new token and assigning it to a user's address.

---

### Disclaimer

This project is for educational and demonstration purposes only. It does not interact with any real blockchain, and no real cryptocurrencies or NFTs are used.
