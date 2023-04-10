# Ethereum Smart Contract Interaction Examples

This repository contains code examples for interacting with Ethereum smart contracts using the ethers.js library and the Infura Ethereum API.

## Part 1: Getting and Setting via Raw Transaction Object

This code demonstrates how to interact with an Ethereum smart contract using raw transaction objects. It uses the ethers.js library and the Infura Ethereum API.

First, it imports the necessary dependencies and sets up the provider, which connects to the Ethereum network. It also sets the wallet address and ABI (Application Binary Interface) for the contract.

The `contractInteraction` function is defined, which first creates an instance of the contract using the ethers.Contract constructor, passing in the wallet address and ABI. It then calls the `name()` function on the contract to get the current value of the `name` state variable, and logs it to the console.

Next, it creates a raw transaction object with the desired values for the nonce, gas price, gas limit, from address, to address, value, data, and chain ID. The `data` field is generated by encoding the function call to the contract's `setValue` function, passing in the argument of 10.

A signer is then created using the private key from the .env file, and the `signTransaction` method is called on the signer object, passing in the raw transaction object to sign it.

Finally, the signed transaction is sent using the `provider.sendTransaction` method, and the resulting transaction hash is logged to the console.

## Part 2: Getting and Setting via Signer

This code also demonstrates how to interact with an Ethereum smart contract, but this time using a signer object instead of a raw transaction object. It uses the same dependencies and Infura Ethereum API as Part 1.

The `contractInteraction` function is defined, which first creates an instance of the contract using the ethers.Contract constructor, passing in the contract address and ABI. It then calls the `name()` function on the contract to get the current value of the `name` state variable, and logs it to the console.

Next, it creates a signer using the private key from the .env file, and creates a new instance of the contract using the signer object instead of the provider object. It then calls the `setValue` function on the contract, passing in the argument of 5, and waits for the transaction to be confirmed using the `wait()` method.

Finally, the resulting transaction object is logged to the console.
