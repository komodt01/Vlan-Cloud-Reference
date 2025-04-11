# VLAN Simulation in AWS

## Overview

In AWS, traditional VLAN tagging (802.1Q) is not exposed to the customer within VPCs. Instead, AWS uses subnets, routing tables, and security groups to simulate VLAN-like traffic segmentation.

## TL;DR

| **Where**                            | **Who Assigns VLAN ID**     | **VLAN Tagging Visible?** |
|-------------------------------------|-----------------------------|----------------------------|
| Inside AWS VPC (subnets, EC2, etc.) | AWS (behind the scenes)     | ❌ No — abstracted         |
| AWS Direct Connect / Hybrid Links   | ✅ You (customer-defined)    | ✅ Yes — VLAN tags required |
| ECS ENI Trunking / Outposts         | ✅ You (if configured)       | ✅ Yes — advanced use case  |

## Notes

- AWS abstracts Layer 2 and uses Layer 3 segmentation.
- VLAN tags are only relevant at the edge (e.g., Direct Connect).
