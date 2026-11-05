# Internal KB: Corporate VPN Connectivity Troubleshooting

**Article ID:** KB001422  
**Target Audience:** IT Support Tier 1 / Tier 2  
**Last Updated:** November 2026  

## Issue Description
Users report an inability to establish a secure connection using the corporate Cisco AnyConnect / GlobalProtect VPN client, frequently encountering "Gateway Unreachable" or "MFA Timeout" errors.

## Step-by-Step Diagnostic Path

### 1. Verify Local Internet Connectivity
Before troubleshooting the software client, ensure the user has an active internet connection.
```bash
ping 8.8.8.8
```
*If pings fail, isolate local Wi-Fi or physical ethernet cabling before proceeding.*
### 2. Flush DNS Cache
Stale DNS entries can prevent the VPN client from resolving the gateway domain. Open PowerShell or Command Prompt as an administrator and execute:
```powershell
ipconfig /flushdns
```

### 3. Clear Stale Routing Tables
If the user was recently switched between different remote subnets, clear old route tables:
```powershell
route /f
```
*Note: A system reboot is required immediately following a route table flush.*

### 4. Re-Synchronize Multi-Factor Authentication (MFA)
If the connection times out during authentication:
1. Open the **authenticator app** on the corporate mobile device.
2. Navigate to **Settings** > **Time Sync**.
3. Force a manual clock sync to resolve time-drift validation errors.

## Escalation Path
If the connection still cannot be established after completing steps 1–4, escalate the ticket to the **Network Infrastructure Team** with the user's public IP address and local client logs.
