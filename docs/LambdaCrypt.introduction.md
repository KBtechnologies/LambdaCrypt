# LambdaCrypt
### Introduction
#### Version 0.1a

---

## Core Problem
### Need for a secure Broadband Link
#### Transmitting large amounts of data securely to sites where Internet Access is not possible or desireable.
Most Systems would likely use [two-way](https://en.wikipedia.org/wiki/Satellite_Internet_access#Two-way_satellite-only_communication) or [one-way + alternate uplink](https://en.wikipedia.org/wiki/Satellite_Internet_access#One-way_receive,_with_terrestrial_transmit) setup with [Satellite Internet](https://en.wikipedia.org/wiki/Satellite_Internet_access) but this may either not be feasible or not desireable.
- A [VPN](https://en.wikipedia.org/wiki/Virtual_private_network) like [IPsec](https://en.wikipedia.org/wiki/IPsec#Tunnel_mode), [OpenVPN](https://en.wikipedia.org/wiki/OpenVPN) or [WireGuard](https://en.wikipedia.org/wiki/WireGuard) can only work on bi-directional Network- or Internet Access, not on [half-duplex and/or recieve-only feeds](https://en.wikipedia.org/wiki/Satellite_Internet_access#One-way_broadcast,_receive_only).
  - And whilst Networks like [I2P](https://en.wikipedia.org/wiki/I2P) and [Tor](https://en.wikipedia.org/wiki/Tor_(network)) do add anonymity to it, they basically act like [Proxy Networks](https://en.wikipedia.org/wiki/Proxy_server) and like commercial VPNs [don't increase anonymity nor safety on their own](https://en.wikipedia.org/wiki/Virtual_private_network#Common_misconceptions).

###
##### Also most satellite internet services have [horrible to nonexistant security in terms of information security and encryption](https://www.youtube.com/watch?v=y1tizjuzVzg).
  - This problem also exists with [SPSC](https://www.youtube.com/watch?v=7Zalmk-eZrM) and other services that run on C-Band.
    - Relying solely on an adversaries' incapability to source professional- or military-grade Satcom equipment is just [Security through obscurity](https://en.wikipedia.org/wiki/Security_through_obscurity) with an extra paywall that only deters unskilled hobbyists that can barely follow a walktrough aka. "Skiddies".

###
#### Regular Satellite Feeds & -Technology are not conducive to this task.
Lossy Codecs like MPEG-2 & MPEG-4 work well for audiovisual broadcasting, but they are just codecs for said content and not designed for any other data and payload.
- Furthermore the [Common Scrambling Algorithm](https://en.wikipedia.org/wiki/Common_Scrambling_Algorithm) and [PowerVU](https://en.wikipedia.org/wiki/PowerVu) have been successfully breached and cannot be fixed.
  - Also CSA is hard-baked into the DVB Specification and the only replaceable part is the [Conditional Access Module](https://en.wikipedia.org/wiki/Conditional_access) which only acts as "Key Generator".
  - Security is likely as low as using [Basic Interoperable Scrambling System](https://en.wikipedia.org/wiki/Basic_Interoperable_Scrambling_System) for encryption.
###### These issues basically reduce the useability of Satellite Feeds down to being a more complex version of a [Numbers Station Feed](https://en.wikipedia.org/wiki/Numbers_station).

---

## What does LambdaCrypt do?
### Act as encryption & Decryption System for Broadband Feeds.
#### LambdaCrypt works transparently
- Regardless of the underlying transport & transmission / recieval technology.
- Is designed to be a encryption and decryption system that cab be used as a transparent [Appliance](https://en.wikipedia.org/wiki/Computer_appliance#Types_of_appliances) similar to network equipment like a [Firewall](https://en.wikipedia.org/wiki/Firewall_(computing)) or VPN-[Router](https://en.wikipedia.org/wiki/Router_(computing)).
#### LambdaCrypt does not require any [Upstream](https://en.wikipedia.org/wiki/Upstream_(networking)) or [Return Channel](https://en.wikipedia.org/wiki/Return_channel) like a [Narrowband Internet Connection](https://en.wikipedia.org/wiki/Satellite_Internet_access#One-way_receive,_with_terrestrial_transmit).
- This allows for [Recieve-Only Broadcasts](https://en.wikipedia.org/wiki/Satellite_Internet_access#One-way_broadcast,_receive_only).
  - Of course, a LambdaCrypt Unit may also allow Transmission depending on the configuration.

---

## Design Goals
### Result in a convenient yet powerful appliance that is user-friendly and unobtrusive.
Similar to [FTA Satellite Recievers](https://en.wikipedia.org/wiki/FTA_receiver).
### Enable the highest technically possible security.
This includes:
- [Renewable Security](https://en.wikipedia.org/wiki/Renewable_security)
  - Individualized Per-Device Keys (DK)
    - [RSA](https://en.wikipedia.org/wiki/RSA_(cryptosystem))-[OAEP](https://en.wikipedia.org/wiki/Optimal_asymmetric_encryption_padding) 256kbit
  - Individualized Per-User Keys (UK)
    - [RSA](https://en.wikipedia.org/wiki/RSA_(cryptosystem))-[OAEP](https://en.wikipedia.org/wiki/Optimal_asymmetric_encryption_padding) 8kbit
- Secure Encryption of all Transmissions
  - [One-Time-Pad Encryption Support](https://en.wikipedia.org/wiki/One-time_pad#Perfect_secrecy)
    - Keys have to either be pre-distributed physically or rolled-out post-deployment via an encrypted transmission.
      - In the age of [legitimate 1TB MicroSD cards](https://www.ign.com/articles/the-best-1tb-microsd-cards) the [Key Distribution Problem](https://en.wikipedia.org/wiki/One-time_pad#Key_distribution) is negligible.
  - [AES-256](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) encryption for data feed. 
    - Using [AES-GCM-SIV](https://en.wikipedia.org/wiki/Block_cipher_mode_of_operation#AES-GCM-SIV) and [AES-CBC](https://en.wikipedia.org/wiki/Block_cipher_mode_of_operation#Cipher_block_chaining_(CBC)) modes respectably.
  - [(non-interactive!) Perfect Forward Secrecy](https://en.wikipedia.org/wiki/Forward_secrecy#Non-interactive_forward_secrecy)

###

### Support commonly needed Types of Communications.
#### This includes:
- ##### Broadcasts [from a LamdaCrypt Server to many LamdaCrypt Terminals]
  - Audio [Radio]
  - Video [TV]
  - Data [Multi- & Unicast]
    - General File Transfers [FTPS/SFTP-alike]
    - Key Updates
    - Key Revocations
  - Messages [Telex, Fax, SMS,]
- ##### Transmissions [from a LamdaCrypt Terminal Node to a LamdaCrypt Server]
  - Data Transfers
    - General File Transfers [FTPS/SFTP-alike]
    - Key Updates [if permissible]
    - Key Revocations [if permissible]
- ##### Bidirectional (realtime) Transfers
  - [Conference] Calling 
    - Audio 
    - Video 
    - Data Streaming

---

## Intended Use-Cases
### Diplomatic Communications
In lieu of backdoored & unauditable appliances like CRYPTO AG (and successor/competitor's) solutions.

## Sensitive Communications of all Kinds

---
