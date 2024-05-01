## Celo CLI (Cheat Sheet)

### Make ERC20 transfer with gas currency

You can see USDC as an EasyFee is live on mainnet using the latest `@celo/celocli` release (v5.0.0):

```sh
# Install latest celocli
$ yarn global add @celo/celocli@5.0.0

# Check fee currencies on mainnet
$ celocli network:whitelist --node mainnet

Available currencies:
0x2F25deB3848C207fc8E0c34035B3Ba7fC157602B - USDC (USDC) (adapted token: 0xcebA9300f2b948710d2653dD7B07f33A8B32118C)
0x73F93dcc49cB8A239e2032663e9475dd5ef29A08 - ECO CFA (eXOF)
0x765DE816845861e75A25fCA122bb6898B8B1282a - Celo Dollar (cUSD)
0xD8763CBa276a3738E6DE85b4b3bF5FDed6D6cA73 - Celo Euro (cEUR)
0xe8537a3d056DA446677B9E9d6c5dB704EaAb4787 - Celo Brazilian Real (cREAL)
```

Send 0.01 USDC using USDC as gas currency on alfajores

```sh
$ celocli transfer:erc20 --erc20Address 0x2F25deB3848C207fc8E0c34035B3Ba7fC157602B --from 0x303C22e6ef01CbA9d03259248863836CB91336D5 --to 0x5111A8caCa3366389EeaAad8a49027d573588BbB --value 0.01e6 --privateKey $PRIVATE_KEY --node alfajores --gasCurrency=0x4822e58de6f5e485eF90df51C41CE01721331dC0

[...]

All checks passed
SendTransaction: transfer
txHash: 0xc83512dc9dbfa9bc29f7467e2cced13f7dda547fc13525fe3d123455dfb32f37
Sending Transaction: transfer... done
```

## Get core contract addresses

```sh
$ celocli network:contracts --node alfajores --columns "Contract","Proxy","Implementation"
 Contract                Proxy                                      Implementation
 ─────────────────────── ────────────────────────────────────────── ──────────────────────────────────────────
 Accounts                0xed7f51A34B4e71fbE69B3091FcF879cD14bD73A9 0x133D9408098b72a18B6c79f06BC62965D1B59cC1
 Attestations            0xAD5E5722427d79DFf28a4Ab30249729d1F8B4cc0 0xA758e8f4f79AB72184914343CaAb2E2162fdDd3D
 BlockchainParameters    0xE5aCbb07b4Eed078e39D50F66bF0c80cF1b93abe 0x029d8a20D86157F47CcbEE5209DEe0591dD2eB70
 DoubleSigningSlasher    0x88A4c203C488E8277f583942672E1aF77e2B5040 0xF06EF728067dd7b5CC752DC0C787dABECcBfC82e
 DowntimeSlasher         0xf2224c1d7b447D9A43a98CBD82FCCC0eF1c11CC5 0xdF3d2CD57090B3B6C15c18Ec7C1E33DCF565B449
 Election                0x1c3eDf937CFc2F6F51784D20DEB1af1F9a8655fA 0x2a39E41a736D3d6d8b7C393397969BaAc8E53DC9
 EpochRewards            0xB10Ee11244526b94879e1956745bA2E35AE2bA20 0xd894682B96B1E5954223e0554afad14b2a93cDdb
 Escrow                  0xb07E10c5837c282209c6B9B3DE0eDBeF16319a37 0xa34117B48313dE0093d599720998415bAb5FD61d
 FederatedAttestations   0x70F9314aF173c246669cFb0EEe79F9Cfd9C34ee3 0x926E88a280902Bfff5047693B9CeAfdb9F4d5095
 FeeCurrencyWhitelist    0xB8641365dBe943Bc2fb6977e6FBc1630EF47dB5a 0x8DE5E4c86284F46a4b034a2F9a41A6175523daa9
 FeeHandler              0xEAaFf71AB67B5d0eF34ba62Ea06Ac3d3E2dAAA38 0x31788a65f0e8318d6b2A36B9dE5Dfc4D1C22F182
 Freezer                 0xfe0Ada6E9a7b782f55750428CC1d8428Cd83C3F1 0x423A32Ee1AF793DF26c4aEe7e36441C00C29e280
 GasPriceMinimum         0xd0Bf87a5936ee17014a057143a494Dc5C5d51E5e 0x31b1Da7073576A3EdC402607B87B4e95539D7FE5
 GoldToken               0xF194afDf50B03e69Bd7D057c1Aa9e10c9954E4C9 0xec6aFE1065c98Fb16E60Cf7764b145bbDE7a2a6c
 Governance              0xAA963FC97281d9632d96700aB62A4D1340F9a28a 0x6b8Ea5A8790eF33421facA99D6855D6444766CF8
 LockedGold              0x6a4CC5693DC5BFA3799C699F3B941bA2Cb00c341 0xF7B828aB943759BF05355A5F4F13D516CD45B4Ee
 MentoFeeHandlerSeller   0xae83C63B5FB50C353c8d23397bcC9dBf3a9837Ac 0x4ec74B45BCCc7f57F434BbFfaEa068f70637fC91
 OdisPayments            0x645170cdB6B5c1bc80847bb728dBa56C50a20a49 0x72eAC1F0518213Ad405560eFd3fB647FbDAdb703
 Random                  0xdd318EEF001BB0867Cd5c134496D6cF5Aa32311F 0x67c6829506DdF66Ed824Fd1cCC40665588Bc4631
 Registry                0x000000000000000000000000000000000000ce10 0x33011E0a33AF1F757396f2a5A1F2158bEd179Dfd
 Reserve                 0xa7ed835288Aa4524bB6C73DD23c0bF4315D9Fe3e 0x5B4B6ba128c7BA51d63eD7474A7b17492Fb28476
 SortedOracles           0xFdd8bD58115FfBf04e47411c1d228eCC45E93075 0xB07A33093d332f0D2810b36Bdd3c9e7390624F1F
 StableToken             0x874069Fa1Eb16D44d622F2e0Ca25eeA172369bC1 0x3Bd899048f4f6951fFeB5474205B79FDB09D6212
 StableTokenBRL          0xE4D517785D091D3c54818832dB6094bcc2744545 0x3Bd899048f4f6951fFeB5474205B79FDB09D6212
 StableTokenEUR          0x10c892A6EC43a53E45D0B916B4b7D383B1b78C0F 0x3Bd899048f4f6951fFeB5474205B79FDB09D6212
 UniswapFeeHandlerSeller 0xc7b6E77C3702666DDa8EB5b7F30234B020788b21 0x1365f75d7087D997F504f56f2CA60418d9970163
 Validators              0x9acF2A99914E083aD0d610672E93d14b0736BBCc 0xF17D8624e0c3402D02b6F8D5870Fff0Dd35e4f0B
```

### Get network parameters

```sh
$ celocli network:parameters --node alfajores
#...
EpochRewards:
  carbonOffsetting:
    factor: 0.25
    partner: 0x22579CA45eE22E2E16dDF72D955D6cf4c767B0eF
#...
```

## Use

Cheat sheet:

- use `--node https://forno.celo.org` to use forno node
- use `--help` for useful options whenever you're stuck
- use `--columns=Name,Version,State` to restrict what's displayed
- use `--sort=-Version` to sort by field
- use `--filter=State=Valid` to filter by field value

Official docs: [CELO CLI](https://docs.celo.org/command-line-interface/introduction)

## Install

```bash
npm -g install @celo/celocli
```

(`-g` means celocli will be installed globally on your device)

### Update

```bash
npm update -g @celo/celocli
```

### Options menu and help

Use `--help` to see a range of options if you're stuck

```bash
$ celocli --help
```

### Autocomplete feature (very useful!)

Run `celocli autocomplete` for instructions (see
[here](https://docs.celo.org/command-line-interface/autocomplete) for the command docs).

```bash
$ celocli autocomplete
$ printf "$(celocli autocomplete:script zsh)" >> ~/.zshrc; source ~/.zshrc
```

Output when setting this up first:

```bash
Building the autocomplete cache... done

Setup Instructions for CELOCLI CLI Autocomplete ---

1) Add the autocomplete env var to your zsh profile and source it
$ printf "$(celocli autocomplete:script zsh)" >> ~/.zshrc; source ~/.zshrc

NOTE: After sourcing, you can run `$ compaudit -D` to ensure no permissions conflicts are present

2) Test it out, e.g.:
$ celocli <TAB>                 # Command completion
$ celocli command --<TAB>       # Flag completion

Enjoy!
```

## Test `MultiSig.sol` with local celocli build

Source:
[github.com > [cli] Add multisig:approve #10693](https://github.com/celo-org/celo-monorepo/pull/10693#pullrequestreview-1720757356)

Steps to test `celocli multisig` on Alfajores.

### Create a MultiSig on Alfajores using Celo Terminal

1.  Download [Celo Terminal](https://celoterminal.com/)
2.  Run this in your CLI (this will start Celo Terminal on Alfajores, instead of Mainnet)

```
export CELOTERMINAL\_NETWORK\_ID=44787
export CELOTERMINAL\_ACCOUNTS\_DB=home/.celoterminal/celoaccounts-test.db
/Applications/Celo\\ Terminal.app/Contents/MacOS/Celo\\ Terminal
```

3.  Add 2 "standard accounts" (the multisig will need two owners for testing)
4.  Create a Multisig ("Add account" > "Create a MultiSig account", set both accounts as owners)

[![image](https://user-images.githubusercontent.com/46296830/281396517-7890c21b-5fc3-4bba-90e1-9bd9e18e9c2a.png)](https://user-images.githubusercontent.com/46296830/281396517-7890c21b-5fc3-4bba-90e1-9bd9e18e9c2a.png)

5.  Faucet your new MultiSig ([faucet.celo.org](https://faucet.celo.org/))

### Make a test transfer from the MultiSig

6.  Make a test transfer from the MultiSig (to anywhere, e.g. one of your standard accounts)

[![image](https://user-images.githubusercontent.com/46296830/281396362-85627ff5-d17f-4162-bab8-7a695b0e4260.png)](https://user-images.githubusercontent.com/46296830/281396362-85627ff5-d17f-4162-bab8-7a695b0e4260.png)

### Approve the MultiSig transfer from the CLI

7.  Checkout branch

```
git checkout timmoreton/multisig-approve-cli
```

8.  [Build branch](https://github.com/celo-org/celo-monorepo/blob/master/SETUP.md#building-celo-monorepo)

```
yarn
yarn build --ignore docs
```

9.  Navigate to locally built CLI package

```
cd packages/cli
```

10. [Set RPC node and network to Alfajores](https://docs.celo.org/cli#optional-run-a-full-node) (for
    testing)

```
bin/run config:set https://alfajores-forno.celo-testnet.org
```

11. Check RPC node and network is set

```
bin/run config:get

node: https://alfajores-forno.celo-testnet.org
gasCurrency: auto
```

12. Confirm the MultiSig transaction is queued (I'm using my test MultiSig created above)

```
bin/run multisig:show 0x37A6bA9CFC3C4C7f82bDf1Fe1B7cEb410E78738E

Owners:
  0: 0x303C22e6ef01CbA9d03259248863836CB91336D5
  1: 0xEb08a36D153827CC750dd264c9e7360A3174Dc27
Required confirmations: 2
Required confirmations (internal): 2
Transactions: 1
```

13. Approve the transaction (I removed my private key from the command for obvious reasons)

```
bin/run multisig:approve --from 0xEb08a36D153827CC750dd264c9e7360A3174Dc27 --for 0x37A6bA9CFC3C4C7f82bDf1Fe1B7cEb410E78738E --tx 0 --privateKey <privateKey\>

Running Checks:
   ✔  The provided address is an owner of the multisig
   ✔  0 is existing transaction
All checks passed
SendTransaction: approveTx
txHash: 0xfe52b86eff92a715ffe158e0ea6d94274e5e083dcf2f40e8baca6a2c638b655e
Sending Transaction: approveTx... done
```

14. Confirm Multisig transfer worked using transaction hash
    above: <https://alfajores.celoscan.io/tx/0xfe52b86eff92a715ffe158e0ea6d94274e5e083dcf2f40e8baca6a2c638b655e>

✅ Yes, MultiSig balance changed 5 CELO -> 4.5, and 0.5 CELO was transferred from MultiSig to chosen
recipient.

### Test local celocli build on a local anvil fork

Source: ChatGPT

Anvil is designed to simulate a live Ethereum network environment by forking from an existing state
of the blockchain. However, when you fork a network, the forked state is essentially "frozen" at the
block number from when the fork occurred. This means that without additional intervention, the node
does not automatically sync with the ongoing changes in the original network. This is typically not
an issue for tests or interactions that do not depend on subsequent blocks, but for operations that
need ongoing network updates, this can cause problems.

If you only need to bypass the sync checks temporarily to use certain `celocli` commands, you can
disable the sync check. Setting the `NO_SYNCCHECK` environment variable will prevent `celocli` from
failing due to the node appearing out of sync:

```sh
NO_SYNCCHECK=true yarn celocli transfer:celo \
--from 0xf73d7f5A890a131f12E4fB03E50277c49748Cf5E \
--to 0x2ee6F1cB802695F64D0A81284b36179f2886E7C2 \
--value 1e18 \
--privateKey $PRIVATE_KEY \
--node http://127.0.0.1:8545/
Running Checks:
   ✔  Compliant Address
   ✔  Compliant Address
   ✔  Account has at least 1 CELO
All checks passed
SendTransaction: transfer
txHash: 0x44f9468e2b4181fbe5b4df4137d5376cd0a541b74917d0131a703ee4e023446b
Sending Transaction: transfer... done
```

This is also how unit tests for the `celocli` are written

```ts
process.env.NO_SYNCCHECK = "true";
testWithGanache("account:authorize cmd", (web3: Web3) => {
  // ...
});
```

Source:
[cli > src > commands > account > `authorize.test.ts`](https://github.com/celo-org/developer-tooling/blob/e7ac487358c30593cfef0497a7e67325a893ac14/packages/cli/src/commands/account/authorize.test.ts#L10-L12)

For future refernce, the sync checking is done in this helper function:
[celo-org > developer-tooling > packages > cli > src > utils > `helpers.ts`](https://github.com/celo-org/developer-tooling/blob/e7ac487358c30593cfef0497a7e67325a893ac14/packages/cli/src/utils/helpers.ts#L14-L15).
