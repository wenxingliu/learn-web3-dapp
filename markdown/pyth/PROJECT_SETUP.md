{% hint style="tip" %}
We recommend completing both the [Solana 101 pathway](https://learn.figment.io/protocols/solana) and [Build a Solana Wallet](https://learn.figment.io/pathways/solana-wallet) before continuing. A working knowledge of [React hooks](https://reactjs.org/docs/hooks-intro.html) and [TypeScript/JavaScript](https://www.typescriptlang.org/) is also recommended.
{% endhint %}

# 🦺 Important information for your safety

During this Pathway, we will provide you with an opportunity to use the Solana [mainnet-beta cluster](https://docs.solana.com/clusters#mainnet-beta) (hereafter referred to as "mainnet") to perform token swaps with [Jupiter](https://jup.ag), a liquidity aggregator for Solana - which means that **actual funds may be used**. This is **not** a requirement for completing the Pathway.

Be aware that during step 4 of the Pathway ("Wallet implementation"), we will explain how to identify & use the private keys of Solana keypairs. Solana keypairs can be created using the Solana CLI, or with the JavaScript API, or even by using a browser extension wallet such as [Phantom](https://phantom.app).

You should **never** share your private keys with anyone. The simplest and most secure approach to this issue is to create an keypair entirely for the purpose of the following tutorials. The wallet component used in several steps of the Pathway has a toggle switch between "Mock" and "Live". When the toggle is set to "Live", you will be able to provide a [private key](https://solana-labs.github.io/solana-web3.js/classes/Keypair.html). This private key is then kept in the local storage of your web browser, so that you do not need to enter it multiple times. If you are not already familiar with it, read more about [web browser local storage](https://blog.logrocket.com/localstorage-javascript-complete-guide/) to understand where and how this data is kept.

Before proceeding, it is extremely important for you to understand that **if you provide the private key of a Solana account containing mainnet SOL to the wallet component in the Pathway, you are _potentially_ risking the full amount of SOL in that account**. Essentially, whatever funds the liquidation bot has access to can be swapped at any time while the bot is running, without user intervention. This is the power of private keys.

# ♻️ A word on swaps

Because we are working with some fairly new technology, there are some gaps in functionality between the Solana devnet and mainnet. There is quite a large discrepancy in the price of USDC tokens between devnet and mainnet, which we will explain in more detail when it becomes relevant.

Note that in order to perform _any_ swaps on Solana mainnet using this project, you must:

- Own a funded account on mainnet containing an amount of SOL and the USDC SPL token.
- Be on Step 7, "Liquidation bot implementation".
- Toggle the wallet component from "Mock" to "Live", then copy and paste the private key of your funded account into the textinput of the **live** wallet component.
- Finally you can switch the wallet component from devnet to mainnet. This will present you with an alert, warning you that you're going live on mainnet with real economic exposure.

If this doesn't make sense yet, don't worry. This is just a heads up. It will make more sense in the context of the Pathway implementation 😁

---

# 🧑‍💻 Install the Pyth client

{% hint style="tip" %}
This Pathway will only cover use of `@pythnetwork/client`. There are also Rust-, Python-, and EVM-based clients. Refer to the [list of available client libraries](https://docs.pyth.network/consumers/client-libraries) in the Pyth documentation for more.
{% endhint %}

In order to use Pyth, you will need to install the TypeScript/JavaScript library for off-chain applications. It provides the tools to do things like displaying the Pyth price on a website. Whether you're using Gitpod or a local clone of the repo, the installation procedure is the same. Run the terminal command below inside the root directory of the project (`learn-web3-dapp/`) :

```text
yarn add @pythnetwork/client
```

---

# 👻 Install the Phantom wallet extension

Turn your favorite browser into a Web 3 enabled crypto wallet!

Go to <https://phantom.app> and click on the "Add to ..." button which will auto-detect your browser and redirect you to the appropriate extension page:

- Firefox: https://addons.mozilla.org/en-US/firefox/addon/phantom-app/
- Chrome / Brave / Edge: https://chrome.google.com/webstore/detail/phantom/bfnaelmomeimhlpmgjnjophhpkkoljpa?hl=en

Optionally, check out <https://phantom.app/security> to learn more about the security features of Phantom.

---

# 🧩 API keys

**DataHub has discontinued Free accounts**. All Figment Learn pathways now make use of public RPC endpoints only. There is no need to supply an API key to access the public endpoints for Solana.

If you're using a private infractructure provider, you may require an API key to access nodes via their endpoints. Remember to have your API key saved in `/learn-web3-dapp/.env.local`. You can then reference your API key in the pathway code via `process.env.<SOME_VARIABLE_NAME>`.

If you are using the [Solana default public endpoints](https://docs.solana.com/cluster/rpc-endpoints) you do not require an API key, and you can connect directly without any additions to `.env.local`.

{% hint style="tip" %}
If the Next.js development server was running at the time you changed the environment variable's value, you will need to restart the Next.js server to make it aware of the new value. You can do this by pressing `Ctrl+C` in the terminal where the Next.js server is running, then restart it with the command `yarn dev`.
{% endhint %}

---

# 👣 Next Steps

Click on the **Next: Connect to Pyth on Solana** button below.
