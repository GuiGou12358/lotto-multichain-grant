# Jackpot Funding for Lotto Multichain dApp

## Proposal Summary

This proposal seeks funding for the jackpot of Lotto multichain dApp.

The Lotto dApp is very similar to national lotteries. The user chooses numbers and if the numbers match the winning numbers, he wins the jackpot. If there is no winner, the jackpot is put back into play.
We believe that the blockchain is really suited for this use case. All data is registered in the blockchain and can be verified. This is the Web3 version of the lotto.

Currently, the version V1, is live on Astar Network since June 14th 2024. [Lotto dApp V1](https://lucky.substrate.fi/lotto/astar#participate)

A version of the dApp V2, multichain, is deployed on the testnets since November 20th 2024: [Lotto dApp V2 - testnet](https://reorg--lotto-evm.netlify.app/)
The multichain version can be deployed on any EVM chains or Substrate chains with the Contracts pallet.
Players can participate in the lottery on different chains using either EVM or Substrate wallets, competing for the same jackpot in a single draw. The draw and jackpot are common across all chains where the Lotto multichain dApp is deployed.

Everything is automated and decentralized via WASM smart contracts or Solidity smart contracts. These smart contracts communicate with each other.

You can find a presentation of the dApp here: [Lotto dApp Presentation](https://youtu.be/r3iTKy5NOg4)
Another video explains the interaction between smart contracts: [Smart Contracts Interaction](https://youtu.be/jwdbL1Mynw8)

## Impact and Value to the Ecosystem

Ink! smart contracts are one of Polkadot's specialties. These smart contracts are deployed and running using the Contracts pallet of the Substrate blockchains.

The Lotto multichain dApp demonstrates the potential of Ink! smart contracts and highlights Polkadot's strengths:

- Interoperability between its blockchains
- Rich ecosystem with WASM smart contracts on Astar Network
- Offchain computation on Phala Network
- EVM smart contracts on Moonbeam

In addition, the dApp can be deployed on any Layer 2 blockchain that is EVM-compatible, demonstrating Polkadot's openness to other ecosystems.

By making the platform open-source on GitHub, it provides the community with a real-world example of a dApp built with Ink! smart contracts, offering a valuable resource for other developers.

The Lotto dApp has been live since June 2024, attracting 15,500 participants, showing promising engagement even with a modest jackpot.

We believe that such a dApp, free, with its user-friendly interface and straightforward concept, could generate significant interest with a substantial jackpot and drive adoption of the Polkadot ecosystem.

This dApp could create organic growth for the Polkadot ecosystem and its blockchains with an increasing number of addresses and transactions.

The dApp can also be a showcase for the Polkadot DAO as a successful project, 100% made in Polkadot, written by its community, for its community, and funded by the largest DAO in the world.


## Proposal to fund lottery jackpot

To generate significant interest and organic growth in the Polkadot ecosystem, the jackpot must be substantial.
The bigger the jackpot, the bigger the hype.
It's why we would like the DAO allocates 100,000 DOT to the jackpot.

The jackpot will be held by a multisig wallet and the members will be chosen by the DAO (e.g. Head Ambassadors).
No funds will be held by the smart contracts, eliminating the risk of token loss.
When there is a winner, the community and our team can verify the draw's validity and the winner's participation before the jackpot is transferred from the multisig to the winner's address.

After one year, if there is no winner, the amount allocated to the jackpot may return to the treasury.

The jackpot amount may be adjusted based on the community feedbacks.

## Parameters of the dApp

The dApp settings should be chosen based on the size of the jackpot.
With a big jackpot, the probability of finding the winning numbers should be low.

With 100,000 DOT as jackpot, we suggest the following parameters:
- The players can choose 6 numbers between 1 and 50. There are more 11 billion possibilities.
- The draw will take place draw every 100 000 blocks (around 1 week).

With these parameters, a spamming attack will not be possible and if someone wants to do it, they will have to pay the transaction fees without any certainty of having the winning numbers.

## Where the dApp will be deployed

The Ink! smart contracts that manages the lottery must be deployed on Astar adn Phala Networks.

However, the contracts that the user interacts to register numbers can be deployed on any EVM chains or Substrate chains with the Contracts pallet.

We suggest to deploy the contracts on Astar, Moonbeam and Soneium.

On Astar Network, the user will be able to play with a Substrate wallet.

On Moonbeam, the user will be able to play with a EVM wallet.

Soneium, the new Layer 2 built by Astar Team and backed by Sony, will be connected to the Superchain. This way the dApp will the first cross-chain dApp between Polkadot and Superchain.

Another important and technical information, in order to make the use of Phala's VRF (Verifiable Random Function) as secure as possible, transaction hashes are used to generate the salt provided to the VRF function.
These transaction hashes are provided by the blockchains where the dApp is deployed.

Even if some hackers found a way to hack the Verifiable Random Function provided by Phala, they would also have to find a way to control the hashes generated by all the blockchains, making the attack much more complicated.
That’s why I suggest deploying the dApp on at least three different blockchains. Of course, we can also deploy these dApps on more blockchains.


## About us and Project Background

Team Lucky is a passionate group of developers and blockchain enthusiasts focused on building decentralized applications (dApps) that bring the power of blockchain to real-world use cases. With a shared commitment to knowledge sharing, community involvement, and advancing the Polkadot ecosystem, Lucky is a perfect blend of expertise, creativity, and technical skills.

GuiGou, a developer with over 20 years of experience, joined the web3 space in 2020 and quickly became involved with the Polkadot ecosystem. Initially an ambassador for Astar Network, he later transitioned to developer roles, contributing to various projects in the ecosystem. GuiGou is the creator of the Lucky dApp, which was rewarded in the Ink! Hackathon (European edition) and is also part of the Ink!ubator program and Phala Builder program. He specializes in Ink! smart contract development, with a strong focus on interoperability, decentralized applications, and blockchain security.

Arno, with his 20 years of experience in web2 development and a deep involvement in the web3 ecosystem since 2021, has worked as an ambassador for Polkadot, Acala, Talisman, and Phala Network. Arno brings a strong background in ecosystem engagement and developer education. He has been instrumental in building user interfaces to interact with smart contracts, integrating EVM and Substrate wallets, optimizing decentralized hosting via IPFS, and ensuring real-time synchronization of the UI with blockchain states.

Together, the Lucky team has participated in multiple hackathons, earning grants and recognition for their work. They have deployed the Lucky dApp on both Astar and Shiden, the Lotto dApp on Astar and are working on expanding the project to bring a decentralized lottery experience to the Polkadot ecosystem and beyond. The team's goal is to make the project community-driven, allowing DAO members to shape the future of the platform and ensure a fully transparent and verifiable lottery experience for all participants.

## Project Overview

Lotto is a multi-chain dApp that includes multiple smart contracts:

- `The Manager`:
  This smart contract, written in Rust and Ink!, is deployed on Astar Network. It knows the state of all other smart contracts and decides what actions to perform for each smart contract. It is the brain of the application.
- `The Communicator`:
  This smart contract, written in Rust and Ink!, is deployed on Phala Network. It enables communication between smart contracts by communicating with the contract manager and transmitting actions to other contracts.
- `The Participation Recorder` (WASM and EVM versions):
  These smart contracts record users' participation in the lottery.
  A version has been written in Rust and Ink! and can be deployed on any Substrate chain where the Contracts pallet is deployed, like Astar Network.
  Another version has been written in Solidity and can be deployed on any EVM-compatible chain like Moonbeam or any Layer 2 like Soneium.

All contracts are battle-tested via unit tests and integration tests.

### Additional Components

- `Subquery Multi-chain Indexer`:
  All data is registered on the blockchain and indexed via a Subquery Multi-chain indexer.
- `User Interface`:
  The user participates in the lottery through an intuitive graphical interface.
- `CLI Tool`:
  A command-line interface tool for deploying and configuring smart contracts and testing the whole scenario.
- `Contract Monitor`:
  A graphical interface that allows visualization of each contract's status during contract synchronization.

## Possible evolution with NFTs integration

NFTs can be integrated to serve as lottery tickets. These NFTs can be periodically airdropped to DOT stakers.
In this way, later, the lottery could be limited only to the holder of these NFTs.
Offering these NFTs to DOT stakers for free could provide an additional use case and increased attractiveness to the DOT token.


## Roadmap

### Short-Term Goals

- Finalize and optimize the dApp to be ready to deploy on mainnet networks.
- Based on community feedbacks, our team will:
- Deploy the smart contracts on the different blockchains.
- Configure the smart contracts with the chosen parameters.
- Set up the indexer and the UI.
- Once the contracts are configured, revoke the admin rights and update the contract owner with the smart contract address.

### Mid-Term Goals

- Integration with mobile wallets (Nova Wallet)
- Implementation of advanced features:
    - NFT-based lottery tickets
    - NFT participation receipts
    - Enhanced user analytics

### Long-Term Goals

- Smart contract-based jackpot distribution system to replace multisig
- Advanced features based on community governance:
    - Multiple lottery pools
    - Special event draws
    - Reward distribution mechanisms


## Conclusion

### Market Opportunity

The traditional lottery market sees millions of weekly players in Web2. Blockchain technology provides the perfect foundation for a transparent, verifiable, and truly fair lottery system. Our dApp bridges this gap between traditional lottery systems and Web3 capabilities.

### Future Vision

The Lotto multichain dApp has the potential to:

- Drive significant adoption of the Polkadot ecosystem
- Demonstrate real-world utility of blockchain technology
- Create a new paradigm for decentralized gaming applications

We appreciate your consideration of this proposal and welcome any feedback from the community.


## Future proposal for retro funding the dApp development

Only if the dApp is a success (functional dApp, positive user feedback, large number of participations), the team will receive a retro funding for the dApp development.

KPIs will be proposed and discussed with the community in order to judge the quality of the development and the dApp.

Some examples of KPI could be :
- at least 100,000 participations and 10,000 different addresses in three months
- a survey with at least 75% positive opinion


A draft for retro funding the dApp development can be found [here](Lotto%20dApp%20-%20Jackpot%20Funding%20-%20draft.md).

The funding request will cover retroactive compensation for completed work and will also allow the team to continue more serenely to evolve and improve the dApp.


## Contact Information

### Team Contacts

- GuiGou: Discord - guigou12358
- Arno: Discord - Arno8443

### Project Links

- Lotto V1 on Astar : [Lotto V1 - mainnet](https://lucky.substrate.fi/lotto/astar#participate)
- Lotto V2 (multichain version) on testnet : [Lotto V2 - testnet](https://reorg--lotto-evm.netlify.app/)
- Demo Videos:
    - [Lotto dApp Presentation](https://youtu.be/r3iTKy5NOg4)
    - [Smart Contracts Interaction](https://youtu.be/jwdbL1Mynw8)


