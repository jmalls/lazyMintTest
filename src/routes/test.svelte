<script>
    import { ThirdwebSDK } from "@thirdweb-dev/sdk";

    async function init() {
        const contract = await sdk.getContract("{{0xE132E26c9d66cDd01d87e530695969B50Ccbfa90}}");

        const contract.claim()
    }
</script>