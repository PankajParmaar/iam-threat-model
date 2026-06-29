---
layout: post
title: "Troubleshooting Azure AD Connect: Resolving Stale Object Sync Failures"
date: 2021-03-10 11:15:00 +0530
categories: [Entra ID, Hybrid Identity]
tags: [aad-connect, directory-sync, idfix, troubleshooting]
author: pankaj
description: "Resolving duplicate UPN and ProxyAddress attributes blocking object synchronization."
---

## Operational Triage Flow
Changes made to user accounts or new mailboxes created in on-premises Active Directory sometimes fail to sync due to duplicate attributes.

1. Run the IdFix tool against your local Active Directory domain controller to scan for errors.
2. Locate the offending user object, open its Attribute Editor tab, and correct or clear the conflicting entry.
3. Run the delta sync command on your Azure AD Connect server to force replication:
   Start-ADSyncSyncCycle -PolicyType Delta
