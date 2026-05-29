# Lab 03: Cloud VPC Security Design

## Objective

Design a basic cloud network using public and private subnets, cloud gateways, and security controls.

## Scenario

A company wants to host a web application in the cloud.

The application needs:

- A public-facing web server
- A private application or database server
- Outbound internet access for private resources
- Private access to cloud storage
- Security rules for HTTPS and SSH
- Clear separation between public and private resources

---

## Proposed Cloud Design

```text
Internet
   |
Internet Gateway
   |
Public Subnet
   |
Web Server

Private Subnet
   |
NAT Gateway
   |
Internet

Private Subnet
   |
VPC Endpoint
   |
Cloud Storage
