---
layout: page
title: Spreading Factor (SF) and Coding Rate (CR)
permalink: /docs/sf-cr/
---

## Why OmaMesh uses Spreading Factor 9 (SF9)

Most LoRa devices ship with a default Spreading Factor of 7 (SF7). While SF7 works well in many lab tests and short-range deployments, OmaMesh users have consistently found that SF9 performs better in real-world conditions across the Omaha metro area.

This is not about chasing maximum range at all costs. It is about reliability.

### The practical reasons for SF9

SF9 strikes a better balance between speed, range, and robustness for our terrain and use cases:

- Improved reliability.
  Better resistance to noise, interference, foliage, buildings, and elevation changes.
- Urban and suburban friendly.
  Omaha's mix of trees, houses, and gentle terrain benefits from the extra link margin.
- Fewer dropped messages.
  Especially noticeable for mobile nodes (bikes, cars, handhelds) and fringe paths.
- Still power efficient.
  Slightly more airtime than SF7, but fewer retries often offset the cost.
- Community consistency.
  A shared SF improves interoperability and makes troubleshooting easier.

---

## A critical rule: Spreading Factor must match

Spreading Factor is not negotiable.

To interoperate on the same mesh, all nodes must use the same Spreading Factor.

If a node is set to SF7 and the rest of the mesh is on SF9, they will not hear each other at all, even if everything else matches.

Think of SF as the language the radios speak:

- Same frequency, channel, and encryption key are not enough.
- If the SF differs, packets are effectively invisible.

This is why OmaMesh strongly recommends SF9 for all nodes joining the network.

---

## What is Spreading Factor?

Spreading Factor (SF) controls how LoRa spreads data across the radio signal:

- Lower SF (e.g., SF7)
  - Faster data rate
  - Shorter range
  - Less tolerant of noise
- Higher SF (e.g., SF9 to SF12)
  - Slower data rate
  - Longer range
  - More tolerant of interference

Each step up in SF increases airtime per packet, improving the odds that distant or obstructed receivers can decode it.

---

## How Coding Rate (CR) works

Coding Rate (CR) controls how much error-correction data is added to each packet.

It answers the question:
"How much redundancy should we add so receivers can fix errors without retries?"

### Coding Rate values

Coding rate is expressed as 4/x, where x ranges from 5 to 8:

- CR 4/5 - minimal redundancy (fastest)
- CR 4/6 - moderate redundancy
- CR 4/7 - higher protection
- CR 4/8 - maximum redundancy (slowest, most robust)

---

## Coding Rate interoperability (important difference)

Unlike Spreading Factor:

Nodes with different Coding Rates can still interoperate.

Receivers can decode packets even if the sender uses a different CR. This allows:

- Repeaters to use higher CR for reliability
- Mobile or battery nodes to use lower CR for efficiency
- Gradual tuning without fragmenting the mesh

In other words:

- SF must match across the mesh
- CR may vary without breaking compatibility

---

## Recommended OmaMesh settings

Default OmaMesh guidance:

- Spreading Factor: SF9 (required)
- Coding Rate:
  - End nodes: default or CR 4/6
  - Repeaters: CR 4/8

This setup has proven to be a reliable, low-drama baseline for:

- Urban and suburban coverage
- Mobile users
- Stable repeater backbones
- Fewer "why can't I hear anyone?" moments

You are always welcome to experiment, but if you want things to just work, start with SF9.

Reliability beats theoretical every time.
