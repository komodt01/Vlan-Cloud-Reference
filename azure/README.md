# VLAN Simulation in Azure

## Overview

Azure does not use VLANs within VNets. Network segmentation is achieved using subnets, route tables, and network security groups (NSGs). VLAN tagging is only used in hybrid connectivity scenarios like ExpressRoute.

## TL;DR

| **Where**                                | **Who Assigns VLAN ID**     | **VLAN Tagging Visible?** |
|-----------------------------------------|-----------------------------|----------------------------|
| Inside Azure VNet (subnets, NSGs, etc.) | Azure (abstracted)          | ❌ No — VLANs not exposed  |
| Azure ExpressRoute (private peering)    | ✅ You (customer-defined)    | ✅ Yes — VLAN tags required |
| Azure Stack / Azure Edge                | ✅ You                      | ✅ Yes — supports VLANs     |
| On-prem to Azure Hybrid Networking      | ✅ You                      | ✅ Yes — VLANs for physical connections |
