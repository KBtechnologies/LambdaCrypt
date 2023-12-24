# LambdaCrypt
### A versatile high-bandwith encryption system

---

## TL;DR:
#### Aimed to be a better alternative to [DVB's](https://en.wikipedia.org/wiki/DVB) [Common Scrambling Algorithm](https://en.wikipedia.org/wiki/Common_Scrambling_Algorithm).
###### It is NOT compatible with the [CI](https://en.wikipedia.org/wiki/Common_Interface) and [CA](https://en.wikipedia.org/wiki/Conditional_access) standards!
- It's more generic in use and designed to fully encrypt all data and not provide any [Chosen Plaintext Attack Vector](https://en.wikipedia.org/wiki/Chosen-plaintext_attack) as would be possible in both [BISS](https://en.wikipedia.org/wiki/Basic_Interoperable_Scrambling_System) and [PowerVu](https://en.wikipedia.org/wiki/PowerVu) as well due to their nature of transmitting MPEG-2 ([as per DVB-S](https://en.wikipedia.org/wiki/DVB-S)) or MPEG-4 ([as per DVB-S2](https://en.wikipedia.org/wiki/DVB-S2)) video streams.
  - Furthermore it's designed with individualized Keys to improve [Renewable Security](https://en.wikipedia.org/wiki/Renewable_security) and deny both [Key Sharing](https://en.wikipedia.org/wiki/Card_sharing) and prevent compromise of the system based off [stolen or lost devices](https://en.wikipedia.org/wiki/Pirate_decryption).

---

## Design Goals
### Be a viable alternative for cross-media transfers
- High-Bandwith Downloads and even Uploads can be facilitated via existing or off-the-shelf Satcom Equipment like [BUCs](https://en.wikipedia.org/wiki/Block_upconverter) and [LNBs](https://en.wikipedia.org/wiki/Low-noise_block_downconverter).
  - This is a relatively stealthy approach to transmitting or at the very least recieving large amounts of data independent from ground infrastructure.
    - Espechally [Recieve-Only](https://en.wikipedia.org/wiki/Satellite_Internet_access#One-way_broadcast,_receive_only) setups may be an option where [Two-Way Satcom](https://en.wikipedia.org/wiki/Satellite_Internet_access#Two-way_satellite-only_communication) isn't an option.
- It also allows for mixed setups where only a [narrowband uplink is available](https://en.wikipedia.org/wiki/Satellite_Internet_access#One-way_receive,_with_terrestrial_transmit).

##### In the end, it should be able to facilitate mono- and bidirectional transfers of data as well as communications.
###

### Be a better Video Conferencing solution
#### Espechally Compared to Commercial Off-The-Shelf Solutions like [Cisco WebEx](https://en.wikipedia.org/wiki/Cisco_Webex)
Most [Videoconferencing](https://en.wikipedia.org/wiki/Videotelephony#Videoconferencing_modes) usually rely on a stable broadband internet connection and either publicly accessible Servers or a Stable [VPN](https://en.wikipedia.org/wiki/Virtual_private_network) connection to the datacenter where these are hosted.
- This may however not always be possible, as internet access may be [illegal](https://en.wikipedia.org/wiki/Internet_in_North_Korea) or not possible due to [lack of appropriate infrastructure](https://en.wikipedia.org/wiki/Telecommunications_in_North_Korea).
###

### Be unobtrusive
#### Discrete Device Design
- Most professional High-Bandwith conferencing systems look like [Profesional Broadcast Equipment](https://upload.wikimedia.org/wikipedia/en/6/60/Headend-rack.jpg) that would look suspicious outside of [TV Broadcasting and Distribution Centers](https://en.wikipedia.org/wiki/Cable_television_headend#Signal_processing).
  - A more discrete design similar to a [Set Top Box](https://en.wikipedia.org/wiki/Set-top_box) or (portable) [blu-ray player](https://en.wikipedia.org/wiki/Blu-ray) may be more desireable.
    - It should also be used by the end-user like one.
###

### Be as secure as possible
#### Highest Security Encryption feasible
- With the existance of [legitimate 1 TB microSD cards](https://www.ign.com/articles/the-best-1tb-microsd-cards) the storage problem of the [One-Time Pad Encryption](https://en.wikipedia.org/wiki/One-time_pad) is negigible.
  - [OTP is basically perfectly secure](https://en.wikipedia.org/wiki/One-time_pad#Perfect_secrecy) in it's encryption and can't be cracked without the key.
- OFC using [OpenPGP](https://en.wikipedia.org/wiki/Pretty_Good_Privacy#OpenPGP) & [GnuPG](https://en.wikipedia.org/wiki/GNU_Privacy_Guard) for encryption, decryption, authentification and digital signatures is still a core part of the system,
  - [AES](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard)[-256](https://en.wikipedia.org/wiki/AES_implementations)[-CBC](https://en.wikipedia.org/wiki/Block_cipher_mode_of_operation#Cipher_block_chaining_(CBC)) encryption can also be utilized for data streams if OTP keys have not been deployed yet.
###

---

## Acknowledgements
### Standards
#### [DVB](https://en.wikipedia.org/wiki/DVB)
- Espechally [DVB-S](https://en.wikipedia.org/wiki/DVB-S), [DVB-S2](https://en.wikipedia.org/wiki/DVB-S2) & [DVB-S2X](https://en.wikipedia.org/wiki/DVB-S2X) for their efficiency in standards in modulating signals.
  - [DVB-RCS](https://en.wikipedia.org/wiki/DVB-RCS) as a standard for Satellite Uplinks, allowing in theory for a multi-vendor & multi-provider market, including different [Satellite Modems](https://en.wikipedia.org/wiki/Satellite_modem).
    - It is [being used by SES Broadband](https://en.wikipedia.org/wiki/SES_Broadband#Technology) for their two-way satellite internet service.
- [DVB-CA](https://en.wikipedia.org/wiki/Conditional_access) as a common yet ultimately insecure system due to using weak [CSA encryption](https://en.wikipedia.org/wiki/Common_Scrambling_Algorithm) and only modularizing the key Generator per [DVB-CI Standard](https://en.wikipedia.org/wiki/Common_Interface).

###
#### [ATSC](https://en.wikipedia.org/wiki/ATSC_standards)
- Most notably for using [8VSB](https://en.wikipedia.org/wiki/8VSB) as modulation system.

###
#### [BISS](https://en.wikipedia.org/wiki/Basic_Interoperable_Scrambling_System)
- As an [EBU](https://en.wikipedia.org/wiki/European_Broadcasting_Union) Standard ([TECH-3292](https://tech.ebu.ch/docs/tech/tech3292.pdf)) that provides an easy way to setup scrambled [SNG](https://en.wikipedia.org/wiki/Satellite_truck) feeds.


##
### Products
#### [PowerVu](https://en.wikipedia.org/wiki/PowerVu)
- For it's per-device encryption keys.

###
#### [SES Broadband](https://en.wikipedia.org/wiki/SES_Broadband)
Two-Way Satellite Internet using [DVB-RCS](https://en.wikipedia.org/wiki/DVB-RCS).

###
#### [tooway](https://en.wikipedia.org/wiki/Tooway)
- Using [Eutelsat](https://en.wikipedia.org/wiki/Eutelsat)'s Satellites for [Ku-Band](https://en.wikipedia.org/wiki/Ku_band) two-way satellite internet as well as 
- [ViaSat KA-SAT](https://en.wikipedia.org/wiki/KA-SAT) on [Ka-Band](https://en.wikipedia.org/wiki/Ka_band) which utilizes 82 different spotbeams with 237 MHz wide transponders, allowing for 475 Mbit/s per spotbeam and due to frequency reuseage, up to 90 Gbit/s of total aggregated bandwith.
  - It uses a modified implementation of [DOCSIS](https://en.wikipedia.org/wiki/DOCSIS) to facilitate the control and bandwith allocations for each [CPE](https://en.wikipedia.org/wiki/Customer-premises_equipment).
    - Basically acting like [Cable Internet](https://en.wikipedia.org/wiki/Cable_Internet_access) over satellite - abeit with high pings due to being hosted on a [GSO](https://en.wikipedia.org/wiki/Geostationary_orbit).
