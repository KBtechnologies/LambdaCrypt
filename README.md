# LambdaCrypt
### A versatile high-bandwith encryption system
#### Aimed to be a better alternative to [DVB's](https://en.wikipedia.org/wiki/DVB) [Common Scrambling Algorithm](https://en.wikipedia.org/wiki/Common_Scrambling_Algorithm).
###### It is NOT compatible with the [CI](https://en.wikipedia.org/wiki/Common_Interface) and [CA](https://en.wikipedia.org/wiki/Conditional_access) standards!
- It's more generic in use and designed to fully encrypt all data and not provide any [Chosen Plaintext Attack Vector](https://en.wikipedia.org/wiki/Chosen-plaintext_attack) as would be possible in both [BISS](https://en.wikipedia.org/wiki/Basic_Interoperable_Scrambling_System) and [PowerVu](https://en.wikipedia.org/wiki/PowerVu) as well due to their nature of transmitting MPEG-2 ([as per DVB-S](https://en.wikipedia.org/wiki/DVB-S)) or MPEG-4 ([as per DVB-S2](https://en.wikipedia.org/wiki/DVB-S2)) video streams.
  - Furthermore it's designed with individualized Keys to improve [Renewable Security](https://en.wikipedia.org/wiki/Renewable_security) and deny both [Key Sharing](https://en.wikipedia.org/wiki/Card_sharing) and prevent compromise of the system based off [stolen or lost devices](https://en.wikipedia.org/wiki/Pirate_decryption).

## Design Goals
### Be a viable alternative for cross-media transfers
- High-Bandwith Downloads and even Uploads can be facilitated via existing or off-the-shelf Satcom Equipment like [BUCs](https://en.wikipedia.org/wiki/Block_upconverter) and [LNBs](https://en.wikipedia.org/wiki/Low-noise_block_downconverter).
  - This is a relatively stealthy approach to transmitting or at the very least recieving large amounts of data independent from ground infrastructure.
    - Espechally Recieve-Only setups may be an option where [Two-Way Satcom](https://en.wikipedia.org/wiki/Satellite_Internet_access#Two-way_satellite-only_communication) isn't an option.
- It also allows for mixed setups where only a [narrowband uplink is available](https://en.wikipedia.org/wiki/Satellite_Internet_access#One-way_receive,_with_terrestrial_transmit).

##### In the end, it should be able to facilitate mono- and bidirectional transfers of data as well as communications.

### Be a better Video Conferencing solution
#### Espechally Compared to Commercial Off-The-Shelf Solutions like [Cisco WebEx](https://en.wikipedia.org/wiki/Cisco_Webex)
Most [Videoconferencing](https://en.wikipedia.org/wiki/Videotelephony#Videoconferencing_modes) usually rely on a stable broadband internet connection and either publicly accessible Servers or a Stable [VPN] connection to the datacenter where these are hosted.
- This may however not always be possible, as internet access may be [illegal](https://en.wikipedia.org/wiki/Internet_in_North_Korea) or not possible due to [lack of appropriate infrastructure](https://en.wikipedia.org/wiki/Telecommunications_in_North_Korea).

### Be unobtrusive
#### Discrete Device Design
- Most professional High-Bandwith conferencing systems look like [Profesional Broadcast Equipment](https://upload.wikimedia.org/wikipedia/en/6/60/Headend-rack.jpg) that would look suspicious outside of [TV Broadcasting and Distribution Centers](https://en.wikipedia.org/wiki/Cable_television_headend#Signal_processing).
  - A more discrete design similar to a [Set Top Box](https://en.wikipedia.org/wiki/Set-top_box) or (portable) [blu-ray player](https://en.wikipedia.org/wiki/Blu-ray) may be more desireable.
    - It should also be used by the end-user like one.

### Be as secure as possible
#### Highest Security Encryption feasible
- With the existance of [legitimate 1 TB microSD cards](https://www.ign.com/articles/the-best-1tb-microsd-cards) the storage problem of the [One-Time Pad Encryption](https://en.wikipedia.org/wiki/One-time_pad) is negigible.
  - [OTP is basically perfectly secure](https://en.wikipedia.org/wiki/One-time_pad#Perfect_secrecy) in it's encryption and can't be cracked without the key.
- OFC using [OpenPGP](https://en.wikipedia.org/wiki/Pretty_Good_Privacy#OpenPGP) & [GnuPG](https://en.wikipedia.org/wiki/GNU_Privacy_Guard) for encryption, decryption, authentification and digital signatures is still a core part of the system,
  - [AES](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard)[-256](https://en.wikipedia.org/wiki/AES_implementations)[-CBC](https://en.wikipedia.org/wiki/Block_cipher_mode_of_operation#Cipher_block_chaining_(CBC)) encryption can also be utilized for data streams if OTP keys have not been deployed yet.
