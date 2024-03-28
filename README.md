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

Use `--help` to see a range of options if you're stuck (thanks @Alec Schaefer 🙌  )

```bash
$ celocli --help
```

### Autocomplete feature (very useful!)

Run `celocli autocomplete` for instructions (see [here](https://docs.celo.org/command-line-interface/autocomplete) for the command docs). (thanks @Eela Nagaraj 👩‍💻 )

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

### Get current-attestation-services

Fields:
- Address 
- Affiliation
- Name
- State
- Version
- Attestationserviceurl
- Smsproviders

Versions: 

```bash
celocli identity:current-attestation-services --node https://forno.celo.org --columns=Name,Version,State --sort=-Version --filter=State=Valid

Fetching currently elected Validators... done
Name                     Version State 
Figment Networks 1       1.5.0   Valid 
Figment Networks 2       1.5.0   Valid 
Figment Networks 3       1.5.0   Valid 
Figment Networks 4       1.5.0   Valid 
Tessellated Geometry     1.5.0   Valid 
                         1.5.0   Valid 
                         1.5.0   Valid 
censusworks.0            1.5.0   Valid 
censusworks.2            1.5.0   Valid 
```

Addresses:

```bash
celocli identity:current-attestation-services --node https://forno.celo.org --columns=Name,Version,Address,State --sort=-Version --filter=State=Valid

Fetching currently elected Validators... done
Name                     Version Address                                    State 
Figment Networks 1       1.5.0   0x0e47ea88480788289bDa37D8Ae0C2CD680623cfA Valid 
Figment Networks 2       1.5.0   0x90b056B00952d71bC7866c067b49f5b062098ac9 Valid 
Figment Networks 3       1.5.0   0xDdc60B465c204Aa7358cE4f009D2dBC65af5C4B4 Valid 
Figment Networks 4       1.5.0   0x12125D1b7f01F32b3A741A6b97CB46f714f273aA Valid 
Tessellated Geometry     1.5.0   0x44a7Af700ACa1B24ECdB818dF4D202772D606Cb4 Valid 
                         1.5.0   0xFEA3a9f2b28E9EeA5EB14bE130c7C79459B2AA5e Valid 
```

## Attestation Service HTTP Endpoints

Here is a list of HTTP endpoints each attestation service exposes: 
- POST /attestations
- POST /test_attestations
- GET /get_attestations
- POST /delivery_status_nexmo [v1.5.0+]
- POST /delivery_status_twilioverify [v1.5.0+]
- POST /delivery_status_twiliomessaging [pre-v1.5.0]
- POST /delivery_status_twilio [v1.2.0+]
- GET /delivery_status_messagebird [not POST]
- GET /status 
- GET /healthz [optional]
- GET /metrics [optional]

Source: [Celo docs > attestation-service > deployment-architecture](attestation-service#deployment-architecture)

This is how to find the attestation service URL: 

```bash
celocli identity:current-attestation-services --node https://forno.celo.org --columns=Name,State,Attestationserviceurl --sort=-Version

Name                                                      State                         Attestationserviceurl                                  
cnstnt.xyz/rc1/validator-1                                NoAttestationSigner           null                                                   
cnstnt.xyz/rc1/validator-2                                NoAttestationSigner           null                                                   
cnstnt.xyz/rc1/validator-3                                NoAttestationSigner           null                                                   
Nodito Labs 1                                             UnreachableAttestationService https://celo-attestation-1.noditolabs.com:3000         
                                                          MetadataTimeout               null                                                   
                                                          MetadataTimeout               null                                                   
                                                          MetadataTimeout               null                                                   
                                                          MetadataTimeout               null                                                   
                                                          MetadataTimeout               null                                                   
SeedBed                                                   NoAttestationSigner           null                                                   
Binance-Staking                                           NoAttestationSigner           null                                                   
Binance-Staking-2                                         NoAttestationSigner           null                                                   
T-Systems MMS 4 delegation from business only Validator 1 NoAttestationSigner           null                                                   
T-Systems MMS 4 delegation from business only Validator 2 NoAttestationSigner           null                                                   
T-Systems MMS 4 delegation from business only Validator 3 NoAttestationSigner           null                                                   
T-Systems MMS 4 delegation from business only Validator 4 NoAttestationSigner           null                                                   
T-Systems MMS 4 delegation from business only Validator 5 NoAttestationSigner           null                                                   
Figment Networks 1                                        Valid                         https://attestations-01.celo.figment.network           
Figment Networks 2                                        Valid                         https://attestations-008.celo.figment.network          
Figment Networks 3                                        Valid                         https://attestations-009.celo.figment.network          
Figment Networks 4                                        Valid                         https://attestations-02.celo.figment.network    
```

Here is an example JSON payload for the /status HTTP endpoint (https://attestations-008.celo.figment.network/status)

```json
{
  "status": "ok",
  "smsProviders": [
    "messagebird",
    "twilioverify",
    "twiliomessaging",
    "nexmo"
  ],
  "blacklistedRegionCodes": [],
  "accountAddress": "0x90b056B00952d71bC7866c067b49f5b062098ac9",
  "version": "1.5.0",
  "latestBlock": 12561402,
  "ageOfLatestBlock": 4.062000036239624,
  "isNodeSyncing": false,
  "appSignature": "x",
  "smsProvidersRandomized": false,
  "maxDeliveryAttempts": 3,
  "maxRerequestMins": 1440,
  "twilioVerifySidProvided": true
}
```
