# nft-mint-concordium

In this project, we are going to mint and transfer a NFT on Concordium blockchain

Instructions

After to do the git clone, update the field "account" in the nft-artificat files with your wallet account address

Deploy your smart contract

- Import your wallet command

  concordium-client config account import <Wallet.export> --name <Your-Wallet-Name>.json

- Deploy the contract command

  concordium-client module deploy dist/cis2.module.wasm.v1 --sender <YOUR-ADDRESS> --name <YOUR-MODULE-NAME> --grpc-port 20001

- Initializing the smart contract

  concordium-client contract init <YOUR-MODULE-NAME> --sender <YOUR-ADDRESS> --energy 30000 --contract <CONTRACT-NAME> --grpc-ip 127.0.0.1 --grpc-port 20001

- Mint function

  concordium-client contract update <YOUR-INDEX> --entrypoint mint --parameter-json nft-artifacts/token-ids.json --schema dist/schema.bin --sender <YOUR-ADDRESS> --energy 6000 --grpc-port 20001

- View function

  concordium-client contract invoke <YOUR-INDEX> --entrypoint view --schema dist/schema.bin --grpc-port 20001
  concordium-client contract invoke <YOUR-INDEX> --entrypoint tokenMetadata --parameter-json nft-artifacts/token-ids.json --schema dist/schema.bin --grpc-port 20001

After we deployed and interacted with it. We can also check the dashboard to see the status of the mint operation

- Module successfully deployed with reference: https://dashboard.testnet.concordium.com/lookup/84648bea373a77b7689080ad0fd59f225b5c058993572cfbe5853b39ac185c39
- Mint status: https://dashboard.testnet.concordium.com/lookup/81ef7c761a0f9472b6f6e857c82f73a4fdd7901914b15c15fe8b11926b6cd153
- Transfer status: https://dashboard.testnet.concordium.com/lookup/e097a3f0a4f18df4908dfa27316003bcb83eef8b855c3108feb8f758c8d62b55
  
  
 # What is next
Next step is to:
1. Implement the dynamic feature to the nft
2. Make the nft soulbounded
