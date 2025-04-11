# VLAN Simulation in GCP

## Overview

GCP VPCs abstract VLANs entirely. Traffic segmentation is performed using subnets, firewall rules, and IAM policies. VLAN tagging is only relevant for edge/hybrid use cases like Dedicated or Partner Interconnect.

## TL;DR

| **Where**                                 | **Who Assigns VLAN ID**     | **VLAN Tagging Visible?** |
|------------------------------------------|-----------------------------|----------------------------|
| Inside GCP VPC (subnets, firewall rules) | Google (abstracted)         | ❌ No — VLANs not exposed  |
| GCP Dedicated/Partner Interconnect       | ✅ You (customer-defined)    | ✅ Yes — VLAN tags required |
| On-prem to GCP Hybrid Networking         | ✅ You                      | ✅ Yes — for traffic segregation |
