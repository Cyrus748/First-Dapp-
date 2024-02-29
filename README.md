# First-Dapp-
This repository is a beginner friendly and for blockchain starter. We will create our first Dapp with the help of learnweb3.io


#Prerequsite
Download and setup MetaMask if you do not have it already

Click on the User Icon at the top-right of MetaMask, go to Settings, and turn on Show Test Networks

Click on Ethereum Mainnet at the top of MetaMask and change it to Sepolia test network

Request some Sepolia Testnet ETH from a faucet like this one - Ethereum Sepolia Faucet | Free 0.1 sETH per day | LearnWeb3

Install a code editor (We recommend Visual Studio Code)

Install Node.js if you do not have it already (Use the LTS version, as that is stable. The latest version is experimental and may have bugs)

Open up a terminal (Command Prompt on Windows, Terminal on macOS or Linux) and install lite-server so you can run your website

npm install -g lite-server


#Building the webpage

The first thing we will do is build out a basic webpage.

Create a new folder on your computer, and open that folder in your code editor. Inside that folder, create a new file - index.html - and open that in your code editor.

Each HTML page has some basic boilerplate we need to write to tell the web browser that this is an HTML document. Add the following to index.html.

If everything was set up properly, your webpage should now be accessible! Go to http://localhost:3000/ to see your page!

We have our boilerplate frontend website ready!

#Build the smart contract

Now it is time to write a simple Solidity smart contract. You can use any editor you like, but for now we recommend using Remix.

Inside Remix, create a new contract file named Mood.soland write the following code:

![alt text](https://github.com/Cyrus748/First-Dapp-/blob/main/assets/soliditypreview.jpeg?raw=true)

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.19;

contract MoodDiary {
    string mood;

    function setMood(string memory _mood) public {
        mood = _mood;
    }

    function getMood() public view returns (string memory) {
        return mood;
    }
}

Make sure your MetaMask is set to the Sepolia Test Network

In Remix's Compile Tab, select the right compiler version to match your Solidity Code (0.8.19 right now)

Compile the code using the Compiler tab

Deploy the contract under the "Deploy and Run Transactions" tab

Under the Deployed Contracts section, you should now see your contract and be able to test out its functions

Be sure to deploy on Sepolia via Remix under the Injected Provider - MetaMask environment and confirm the deployment transaction in MetaMask.

Now, take note of the address and ABI of the contract you just deployed - we will need this on our frontend. You can copy the contract address by clicking the Copy button next to the deployed contracts pulldown in Remix. You can copy the ABI under the contract in Remix's Compile tab.

#Connect your webpage to your smart contract

Now, let's go back to index.html in your code editor. Here, we will do a few things:

Add ethers.js as an external library to your code

Use ethers.js to create a reference to the deployed Solidity contract

Call your contract's functions through MetaMask with the help of ethers.js

At the beginning (or end) of your HTML file, import ethers.js library as follows, and add a second empty script tag for your own JavaScript code

#Let's try it out!

If you followed the steps properly, your webpage should now be able to call the getMood and setMood functions on your smart contract!

Make sure your web server is still running at http://localhost:3000 - if not, restart lite-server through your Terminal.

Go to your webpage and test your functions and approve the transactions as needed through your MetaMask wallet!

See your contract and transaction information via https://sepolia.etherscan.io/

Open a console ( Ctrl + Shift + I ) in your web browser to see the magic happen as you press those buttons!

#Congratulations

Amazing! If you got this far, that means you just made a simple website that interacts with a real, live Ethereum testnet on the internet. This is not something many folks can say they have done!

If you have trouble at any step of the way and cannot figure it out, reach out to us on our Discord Server and ask for help! We'll be sure to help you out!
