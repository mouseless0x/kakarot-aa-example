# Setup Mock AA environment

Start anvil:

```bash
anvil --chain-id 1802203764
```

Deploy all contracts:

```bash
pnpm run start
```

## Contracts

`src/index.ts` will deploy the following contracts:

- Deterministic Deployer (Non EIP-155): `0xac19aa389d94E8b74dD25bd25C9F1DE96e812402` ([source code](https://github.com/Arachnid/deterministic-deployment-proxy))

- EntryPoint V0.6: `0x027b465F1Cfc3B2A70611587d3eE06362AA14E3a` ([source code](https://github.com/eth-infinitism/account-abstraction/blob/releases/v0.6/contracts/core/EntryPoint.sol))

- SimpleAccountFactory V0.6: `0xA3f44eF06ECccf45CfcF38920cB9e0FD23A66E31` ([source code](https://github.com/eth-infinitism/account-abstraction/blob/releases/v0.6/contracts/samples/SimpleAccountFactory.sol))

- Counter Factual SmartAccount Address: `0xE1308369167a65CDEFC1247c812eeeB705237018` ([source code](https://github.com/eth-infinitism/account-abstraction/blob/releases/v0.6/contracts/samples/SimpleAccount.sol))


## Making Raw HandleOp Call

```bash
cast send 0x027b465F1Cfc3B2A70611587d3eE06362AA14E3a \
    0x1fad948c0000000000000000000000000000000000000000000000000000000000000040000000000000000000000000433704c40f80cbff02e86fd36bc8bac5e31eb0c100000000000000000000000000000000000000000000000000000000000000010000000000000000000000000000000000000000000000000000000000000020000000000000000000000000e1308369167a65cdefc1247c812eeeb7052370180000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000016000000000000000000000000000000000000000000000000000000000000001e000000000000000000000000000000000000000000000000000000000000557300000000000000000000000000000000000000000000000000000000000086470000000000000000000000000000000000000000000000000000000000003d090000000000000000000000000000000000000000000000000000000003b9aca000000000000000000000000000000000000000000000000000000000008f0d180000000000000000000000000000000000000000000000000000000000000020000000000000000000000000000000000000000000000000000000000000002200000000000000000000000000000000000000000000000000000000000000058A3f44eF06ECccf45CfcF38920cB9e0FD23A66E315fbfb9cf0000000000000000000000004b4888942bfe98731727d0955cdd42cbecf3dd1900000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000041f94b0f38c0c3481e9597f629e072de8572826438ceb3f8a7fa90ba9f1b0ee2d759912d6b6ede30ec2285e8f1153ea73e3acf1751709c8c323dfebcb87902b27e1b00000000000000000000000000000000000000000000000000000000000000 \
    --gas-limit 1500000 \
    --private-key 0xac0974bec39a17e36ba4a6b4d238ff944bacb478cbed5efcae784d7bf4f2ff80
```

## Raw UserOperation
```json
{
  "sender": "0xE1308369167a65CDEFC1247c812eeeB705237018",
  "nonce": 0n,
  "initCode": "0xA3f44eF06ECccf45CfcF38920cB9e0FD23A66E315fbfb9cf0000000000000000000000004b4888942bfe98731727d0955cdd42cbecf3dd190000000000000000000000000000000000000000000000000000000000000000",
  "callData": "0x",
  "callGasLimit": 350000n,
  "verificationGasLimit": 550000n,
  "preVerificationGas": 250000n,
  "maxFeePerGas": 1000000000n,
  "maxPriorityFeePerGas": 150000000n,
  "paymasterAndData": "0x",
  "signature": "0xf94b0f38c0c3481e9597f629e072de8572826438ceb3f8a7fa90ba9f1b0ee2d759912d6b6ede30ec2285e8f1153ea73e3acf1751709c8c323dfebcb87902b27e1b"
}
```

