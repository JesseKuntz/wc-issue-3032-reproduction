# Reproduction for https://github.com/WalletConnect/walletconnect-monorepo/issues/3032

---

This is a [RainbowKit](https://rainbowkit.com) + [wagmi](https://wagmi.sh) + [Next.js](https://nextjs.org/) project bootstrapped with [`create-rainbowkit`](https://github.com/rainbow-me/rainbowkit/tree/main/packages/create-rainbowkit).

## Getting Started

```
cp .env.template .env.local
```

Fill in `NEXT_PUBLIC_WALLET_CONNECT_PROJECT_ID` with your project ID.

```
pnpm i

pnpm dev
```

Open [http://localhost:3000](http://localhost:3000).

Testing scenarios:

- If you want to connect on Mainnet instead of Goerli, edit the `configureChains` call in `pages/_app.tsx` to use `mainnet` instead of `goerli`.

- If you want the tx to proceed through the Relay to the wallet, edit the `sendTransaction` call in `pages/index.tsx` to use `mockData70KB` instead of `mockData80KB`.

Troubleshooting:

- If you're seeing multiple TXs pop up when sending locally, disable `reactStrictMode` in `next.config.js`.

- If you're using the 70KB version but not seeing the wallet respond right away, that's okay - just make sure that the WebSocket got a response to the `sendTransaction` message and be patient.
