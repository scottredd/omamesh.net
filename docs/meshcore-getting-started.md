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

MeshCore runs on a range of LoRa-capable hardware, but some devices are much better suited to real-world mesh use than others. Below is a curated list of MeshCore-compatible devices that OmaMesh members actively recommend, with a short description of what makes each one useful.

This list emphasizes real deployments, RF performance, and ease of use, not just specs on paper.

---

#### Heltec WiFi LoRa 32 (V2 / V3)

A long-standing favorite and an easy entry point.

- Built-in OLED display
- USB powered, simple flashing
- Widely available and well supported
- Moderate RF output

Best for: beginners, desk nodes, simple fixed nodes

---

#### Heltec WiFi LoRa 32 V4

An updated version with significantly higher RF output power.

- Higher transmit power than earlier Heltec boards
- Improved RF performance overall
- Retains OLED display and USB convenience
- Slightly higher power consumption

Best for: fixed nodes, rooftops, locations where range matters  
Why we like it: noticeably better link reliability than V2/V3

---

#### Heltec Station G2

A purpose-built desktop LoRa station.

- Integrated case, screen, and controls
- Designed for always-on operation
- Strong RF performance
- Clean appliance-like setup

Best for: home base stations, monitoring nodes, repeaters  
Why we like it: polished, stable, and low-maintenance

---

#### LilyGO T-Beam (SX1262)

A community classic with excellent versatility.

- SX1262 radio (very good RF characteristics)
- Built-in GPS
- Battery support and charging
- External antenna connector

Best for: mobile nodes, bikes, vehicles, GPS tracking

---

#### LilyGO T-LoRa32 variants

A simpler, smaller alternative to the T-Beam.

- SX1262 radio
- Lower cost and compact size
- No GPS on most versions
- Good battery options

Best for: compact builds, battery nodes, experimentation

---

#### Seeed T1000-E

A small, rugged tracker-style device.

- SX1262 radio
- Excellent low-power design
- Integrated battery and enclosure
- No Wi-Fi or screen

Important note:  
The T1000-E does not have Wi-Fi and is not ideal for development or debugging, but it performs very well once configured.

Best for: portable nodes, long-runtime carry devices  
Why we like it: efficient, durable, and surprisingly capable

---

#### RAK Mini (RAK4631 Mini)

A compact, low-power LoRa module designed for embedded and portable use.

- SX1262-based radio
- Very small footprint
- Excellent power efficiency

Best for: ultra-compact builds, solar repeaters, embedded projects, advanced users  
Why we like it: great RF performance in a tiny, efficient package

---

#### RAK WisBlock (RAK4631 + Base Board)

A modular, professional-grade platform.

- Excellent RF performance
- Swappable modules (GPS, sensors, power)
- Highly configurable
- Requires light assembly

Best for: repeaters, permanent installs, sensor nodes  
Why we like it: reliability and flexibility at scale

---

#### Generic ESP32 + SX1262 dev boards

A mixed bag depending on vendor and layout.

- Often inexpensive
- RF quality varies widely
- May require tuning and troubleshooting

Best for: tinkerers and advanced experimentation

---

### Choosing the right device

When selecting hardware for OmaMesh and MeshCore, prioritize:

- SX1262 radio (strongly recommended)
- External antenna connector
- Power profile (USB vs battery vs always-on)
- Use case (mobile vs fixed vs repeater)
- Ease of flashing and recovery

Antenna quality and placement often matter more than the board itself.

---

### Compatibility notes (important)

- All devices listed here can run MeshCore firmware
- Spreading Factor must match the mesh (SF9 for OmaMesh)
- Coding Rate may vary without breaking interoperability
- Higher output power does not guarantee better results without good antennas

If you are unsure what to buy, start with a Heltec V4, RAK, Station G2, or T-Beam, then branch out as your needs evolve.

Get on the air first. Optimize later.

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

### Why SF9?

SF9 strikes a good balance for Omaha:

- Better reliability than SF7
- Still reasonably fast
- Improved performance through trees, buildings, and terrain
- More consistent acknowledgements across multiple hops

For details on why SF9 is required and how Coding Rate affects reliability, see
[Spreading Factor (SF) and Coding Rate (CR)]({{ "/docs/sf-cr/" | relative_url }}).
## Your first steps on the mesh

Once your device is configured:

- Power it on and let it run for a few minutes
- Watch for node discovery - you should start seeing nearby stations. It make take a few hours depending on the advert frequency of companion nodes, repeaters, and room servers.
- Find nearby repeaters: in your companion app, navigate to Tools -> Discover Nearby Nodes -> Discover Repeaters. This will ask local repeaters to identify themselves to you.
- Send a short message in the public channel and look for repeats or even replies from other users
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

- OmaMesh MeshCore Discord: https://discord.gg/59sbGSCEms

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
