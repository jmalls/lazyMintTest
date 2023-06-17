<script>

import { BrowserProvider, Contract } from 'ethers';
import { ThirdwebSDK } from "@thirdweb-dev/sdk";
import abi from './abi.json';

const contractAddress = "0xE132E26c9d66cDd01d87e530695969B50Ccbfa90";

async function lazyMint() {
    const provider = new BrowserProvider(window.ethereum);

    provider.send("eth_requestAccounts");

    const signer = await provider.getSigner();
    
    const sdk = ThirdwebSDK.fromSigner(signer);
}

</script>

<h1>Test</h1>

<button on:click={lazyMint}>Lazy Mint</button>