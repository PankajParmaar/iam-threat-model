---
layout: post
title: "Programmatic Tenant Diagnostics: Automating Entra ID Security Assessments"
date: 2026-06-29 19:30:00 +0530
categories: [Entra ID, Security Operations]
tags: [powershell, automation, security-assessment, microsoft-graph]
author: pankaj
description: "A hardened administrative script to rapidly map cross-tenant trust boundaries and identify exposed administrative roles."
---

## Operational Overview
Manual validation of highly privileged cloud directories introduces human oversight windows. This automated routine exposes misconfigured role elevations and untrusted tenant cross-connections.

## Script Execution Block
```powershell
# Connect to Microsoft Graph with specific granular auditing scopes
Connect-MgGraph -Scopes "Directory.Read.All", "Policy.Read.All"
Get-MgDirectoryRole | Select-Object DisplayName, Id
```
