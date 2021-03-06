# Network Components

![](../.gitbook/assets/artboard-copy-14.jpg)

The following is a list of the primary components - hardware, software, protocols, etc. - that make up the end-to-end Helium Network. Complete documentation, code, and other resources for these are linked at the bottom of each section when available.

## Helium blockchain

The Helium blockchain is a new, public, distributed ledger, designed from the ground up to provide an efficient way to run application logic core to the Helium Network. Specifically it furnishes the immutable, append-only transaction system that is verified using the Helium Consensus Protocol \(described in detail below\).

In addition to a new consensus protocol, the Helium blockchain uses a new, novel work algorithm known as [Proof of Coverage](https://github.com/helium/devdocs/tree/67b988ec351854ec4b7608e12b5b8f47f2456abf/blockchain/proof-of-coverage/README.md) to secure the network and cryptographically verify the location of Hotspots that are providing wireless coverage to Helium IoT devices. These [Hotspots](https://github.com/helium/devdocs/tree/67b988ec351854ec4b7608e12b5b8f47f2456abf/hotspot/README.md) are also responsible for submitting coverage proofs that provide details about their true location in and value to the Helium Network. Hotspots that submit the best proofs are more likely to be selected to a consensus group, and are thus responsible for verifying transactions and mining blocks.

## Helium Hotspot

The Helium Hotspot is a combination LoRaWAN wireless router and Helium blockchain miner built and distributed by Helium, Inc. It creates a long-range wireless network for routing packets to and from Helium-enabled devices and performs ongoing mining duties to secure the Helium Network.

It’s expected that developers and manufacturers will build other “Hotspot” variants that conform to published network specifications. “Helium Hotspot” is the name of the Hotspot designed, manufactured, and distributed by Helium, Inc.

### Extended Reading

* [Interactive map of all deployed Hotspots](https://network.helium.com/coverage)
* [Buy a Hotspot and join the Network](https://www.helium.com/store)

## LongFi

LongFi is the top-level architecture that combines the Helium blockchain with the LoRaWAN wireless protocol under the Helium Network umbrella. [Read full details on the LongFi architecture here.](../longfi/introduction.md)

## Routers

Routers are cloud-based participants in the Helium Network and are the termination point for device data. Routers are identifiable by their OUI \(Organizationally Unique Identifier\) and are operated by developers and enterprises deploying sensor applications on the Helium Network. Helium also operates a high-availability router that’s open to Helium Network users.

Devices on the Helium Network are able to send data to one or more routers. When a device sends a packet, the Hotspot that receives it via LoRaWAN queries the blockchain for the router OUI \(or OUIs\) associated with that device. The Hotspot forwards it on, and the target router is then responsible for handling the payload and remitting payment to the Hotspot using Data Credits.

Routers are also the basis for a mechanism called “Channels”. Channels are pre-built integrations with popular cloud services like AWS, Google Cloud, and Azure; and protocols like HTTP\(s\) and MQTT\(s\). Any organization deploying a router can implement custom channels using the reference implementation published by Helium.

## Console

[Console](https://console.helium.com) is a web application built and maintained by Helium. It’s used by developers and enterprises on the Helium network to deploy and manage devices, configure Channels, buy data credits, and more.

Organizations and developers not wanting to use Console can build similar functionality using various APIs exposed by the Helium blockchain and router.

## Blockchain API

The Helium blockchain API enables programmatic access to all data stored in the Helium blockchain. The Helium Mobile Wallet, the Network Visualizer, and the public network Dashboard all make use of this API.

* Full usage and design documentation for the Helium blockchain API is available [here](https://docs.api.helium.io).
* The Blockchain API [source code is on GitHub](https://github.com/helium/blockchain-api/)

## Helium Mobile Wallet

![](../.gitbook/assets/artboard.png)

The Helium Mobile Wallet is the officially supported iOS and Android app used to manage Helium tokens, deploy and administer Hotspots, and view network statistics and visualizations.

The Helium Mobile Wallet is the primary mechanism for deploying Helium Hotspots. A given Hotspot is tied permanently to the Mobile Wallet \(and associated private key\) used to deploy it.

* [Helium Wallet for iOS](https://apps.apple.com/app/id1450463605)
* [Helium Wallet for Android](https://play.google.com/store/apps/details?id=com.helium.wallet&hl=en_US)

## Helium CLI Wallet

Helium maintains and develops a Command Line Interface \(CLI\) for creating and managing Helium wallets. Code and documentation can be found [here](https://github.com/helium/helium-wallet-rs/).

