<script>

import { BrowserProvider, Contract } from 'ethers';
import abi from './abi.json';

const contractAddress = "";

async function lazyMint() {
    const provider = new BrowserProvider(window.ethereum);

    provider.send("eth_requestAccounts");

    const signer = await provider.getSigner();

    const contract = new Contract(abi, contractAddress, signer);
    try {
        const tx = await contract.lazyMint(1, 0, 0);
    } catch (error) {
        console.error(error)
    }
    await tx.wait();
}

</script>

<h1>Test</h1>

<button on:click={lazyMint}>Lazy Mint</button>