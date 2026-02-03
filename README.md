# Packet Squirrel Versions 

There are currently two versions of the Packet Squirrel.  The original Packet Squirrel can be identified by the micro-usb power port, while the Packet Squirrel Mark II can be identified by the USB-C power port.

Please make sure you select payloads for the device you have!

Payloads for the original Packet Squirrel be found in the `legacy-mk1/` directory.

The Packet Squirrel Mark II payloads can be found in the `payloads/` directory.

The Packet Squirrel Mark II expands the DuckyScript for Packet Squirrel commands and adds many new commands and features.  In general, payloads from the original Packet Squirrel can be adapted to run on the Packet Squirrel Mark II by adopting the new commands - check out the [Packet Squirrel Mark II Payload documentation](https://docs.hak5.org/packet-squirrel-mark-ii/payload-development/duckyscript-for-packet-squirrel) for more information!

The existing suite of original Packet Squirrel payloads remains available and functional on the original hardware in the `legacy-mk1/` directory!

<br/>
<h1><a href="https://hak5.org/products/packet-squrirel">About the Packet Squrirel</a></h1>

The Packet Squirrel Mark II by Hak5 is a stealthy pocket-sized man-in-the-middle.

This Ethernet multi-tool is designed to give you covert remote access, painless packet captures, and secure VPN connections with the flip of a switch.

<b>
<div align="center">
<a href="https://www.youtube.com/watch?v=hN9tFx5N3uM">Launch Video</a>
<br/>
<br/>
</div>
</b>
<p align="center">
<a href="https://hak5.org/products/packet-squirrel"><img src="https://3076592524-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F520JUF2JxB2RMXztRVAV%2Fuploads%2F6gSNjJNnaht6yMo5AMCg%2Fsquirrel-setup.png?alt=media&token=382e30a0-10c0-4ab0-88b4-db27e9331a23"></a>
<br/><i>Hak5 Packet Squirrel Features</i>
</p>
<br/>

The Packet Squirrel Mark II is an Ethernet multi-tool for packet capture, man-in-the-middle network manipulation, stream filtering and redirection, remote VPN access, and more.

Use simplified DuckyScript for Packet Squirrel to create payloads, or unlock the full power of Bash script or Python 3 for complex payloads.

Edit payloads live in the Web UI editor with syntax highlighting, SSH, or [build your payloads with Payload Studio](https://payloadstudio.hak5.org).

Exfiltrate data or pentest from anywhere with [Hak5 Cloud C²](https://shop.hak5.org/products/c2 "Hak5 Cloud C²").


## Naming Conventions

Please give your payload a unique, descriptive and appropriate name. Do not use spaces in payload, directory or file names. Each payload should be submit into its own directory, with `-` or `_` used in place of spaces, to one of the categories such as exfiltration, interception, sniffing, or recon. Do not create your own category.

The payload itself should be named `payload`.

Additional files and documentation can be included in the payload directory.  Documentation should be in `README.md` or `README.txt`.

## Payload Configuration

In many cases, payloads will require some level of configuration by the end payload user. Be sure to take the following into careful consideration to ensure your payload is easily tested, used and maintained. 

- Remember to use PLACEHOLDERS for configurable portions of your payload - do not share your personal URLs, API keys, Passphrases, etc...
- Do not leave defaults that point at live services
- Make note of both required and optional configuration(s) in your payload using comments at the top of your payload or "inline" where applicable

## Payload Format

Payloads should begin with comments specifying at the very least the name of the payload and author. Additional information such as a brief description, the target, any dependencies / prerequisites and the LED status used is helpful.

    # Title: Example payload
	# Description: Example payload with configuration options
	# Author: Hak5
	# Version: 1.0
	# Category: Remote-Access
	# Net Mode: NAT
	#
	# LED State Descriptions
	# Magenta Solid - Configuring NETMODE
	# LED OFF - Waiting for BUTTON
	# Red Blink 2 Times - Connection Failed
	# Amber Blink 5 Times - Connection Successful
	# Red Blink 1 Time - Command Failed
	# Cyan Blink 1 Time - Command Successful

### Configuration Options

Configurable options should be specified in variables at the top of the payload file:

    # Options
    SSH_USER="username"
	SSH_HOST="hostname"
    PORT=31337

### NETMODE

All payloads should include a `NETMODE` command to set the Packet Squirrel to a useful network mode.

When in doubt, `NETMODE NAT` is a reasonable default.

### LED

The payload should use common payload states rather than unique color/pattern combinations when possible with an LED command preceding the Stage or `NETMODE`.

	LED SETUP
	NETMODE NAT

Common payload states include a `SETUP`, with may include a `FAIL` if certain conditions are not met. This is typically followed by either a single `ATTACK` or multiple `STAGEs`. More complex payloads may include a `SPECIAL` function to wait until certain conditions are met. Payloads commonly end with a `CLEANUP` phase, such as moving and deleting files or stopping services. A payload may `FINISH` when the objective is complete and the device is safe to eject or turn off. These common payload states correspond to `LED` states.


<h1><a href="https://hak5.org/pages/policy">Legal</a></h1>

Payloads from this repository are provided for educational purposes only.  Hak5 gear is intended for authorized auditing and security analysis purposes only where permitted subject to local and international laws where applicable. Users are solely responsible for compliance with all laws of their locality. Hak5 LLC and affiliates claim no responsibility for unauthorized or unlawful use.

DuckyScript is a trademark of Hak5 LLC. Copyright © 2010 Hak5 LLC. All rights reserved. No part of this work may be reproduced or transmitted in any form or by any means without prior written permission from the copyright owner.
Packet Squirrel and DuckyScript are subject to the Hak5 license agreement (https://hak5.org/license)
DuckyScript is the intellectual property of Hak5 LLC for the sole benefit of Hak5 LLC and its licensees. To inquire about obtaining a license to use this material in your own project, contact us. Please report counterfeits and brand abuse to legal@hak5.org.
This material is for education, authorized auditing and analysis purposes where permitted subject to local and international laws. Users are solely responsible for compliance. Hak5 LLC claims no responsibility for unauthorized or unlawful use.
Hak5 LLC products and technology are only available to BIS recognized license exception ENC favorable treatment countries pursuant to US 15 CFR Supplement No 3 to Part 740.

# Disclaimer
Generally, payloads may execute commands on your device. As such, it is possible for a payload to damage your device. Payloads from this repository are provided AS-IS without warranty. While Hak5 makes a best effort to review payloads, there are no guarantees as to their effectiveness. As with any script, you are advised to proceed with caution.
