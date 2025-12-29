---
layout: page
title: Getting Started with MeshCore (OmaMesh)
permalink: /docs/meshcore-getting-started/
---

Welcome to OmaMesh. This guide will help you get on the air with MeshCore, a lightweight, reliable mesh-messaging system that works well in the Omaha metro and surrounding areas.

You do not need to be a radio expert to get started. If you can configure a device and install an app, you are most of the way there.

## What is MeshCore?

MeshCore is a text-based mesh networking protocol designed for low-power radios. Devices communicate directly with each other and automatically relay messages across multiple hops when needed.

Key features:

- Works without internet or cellular service
- Automatic multi-hop message routing
- Message acknowledgements (you know when it got through)
- Efficient and battery-friendly

Many OmaMesh users run both Meshtastic and MeshCore on different radios or at different times.

## What you need

### 1. A supported radio

You will need a LoRa radio that supports MeshCore firmware. Popular choices include:

- List of devices here
- 
If you are unsure whether your hardware is compatible, ask in the OmaMesh Discord.

### 2. MeshCore software

You will interact with MeshCore using one of the following:

- MeshCore Companion (recommended for most users)
- meshcore-cli (command-line tool for advanced users)

These tools let you:

- Configure your radio
- Send and receive messages
- Discover nearby nodes
- View acknowledgements and routes

### 3. An antenna (important)

Your antenna matters more than almost anything else.

- Use a properly tuned antenna for your frequency band
- Even a small upgrade can dramatically improve range
- Height helps - a window, balcony, or attic can make a big difference

## Recommended OmaMesh radio settings

OmaMesh users have found these settings work better locally than MeshCore defaults.

Radio settings:

- Region: USA / Canada (Recommended)
- Spreading Factor: SF9
- Bandwidth: Leave at preset default
- Coding Rate:
  - End-user nodes: default
  - Repeaters: set to CR 8

After changing settings:

- Save
- Reboot your device

For details on why SF9 is required and how Coding Rate affects reliability, see
[Spreading Factor (SF) and Coding Rate (CR)]({{ "/docs/sf-cr/" | relative_url }}).

### Why SF9?

SF9 strikes a good balance for Omaha:

- Better reliability than SF7
- Still reasonably fast
- Improved performance through trees, buildings, and terrain
- More consistent acknowledgements across multiple hops

Why SF9 explainer here.

## Your first steps on the mesh

Once your device is configured:

- Power it on and let it run for a few minutes
- Watch for node discovery - you should start seeing nearby stations
- Send a short message in the public channel
- Try sending a direct message (DM) to another node
- Look for a delivery acknowledgement (ACK)

If you get an ACK, congratulations - you are on the mesh.

## Mesh etiquette (good neighbor rules)

MeshCore is shared spectrum. A little courtesy goes a long way.

- Keep messages reasonably short
- Avoid rapid repeated transmissions
- Do not spam discovery or status requests
- If running a repeater, use conservative settings
- Remember: everyone shares the same airwaves

## Getting help and staying connected

The Omaha mesh community is friendly and active.

- OmaMesh MshCore Discord: https://discord.gg/59sbGSCEms

If something is not working:

- Ask questions
- Share what hardware and settings you are using
- Someone nearby has probably tried the same thing already

## What is next?

Once you are comfortable:

- Experiment with antennas and placement
- Try running a repeater or room server node
- Explore repeaters and multi-hop routing
- Watch the OmaMesh node map
- Participate in events and experiments

Mesh networks grow stronger with every node. Thanks for being part of OmaMesh.
