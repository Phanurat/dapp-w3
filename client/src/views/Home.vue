<template>
  <div>
    <h2>Welcome to My Dapp</h2>
    <button @click="connectWallet">Connect Wallet</button>
  </div>
</template>

<script>
import { ethers } from 'ethers';

export default {
  name: 'Home',
  methods: {
    async connectWallet() {
      if (window.ethereum) {
        try {
          const provider = new ethers.providers.Web3Provider(window.ethereum);
          await provider.send("eth_requestAccounts", []);
          const signer = provider.getSigner();
          console.log("Wallet connected:", await signer.getAddress());
        } catch (error) {
          console.error("Connection failed:", error);
        }
      } else {
        alert("Please install MetaMask!");
      }
    },
  },
};
</script>

<style>
button {
  margin-top: 20px;
  padding: 10px 20px;
}
</style>
