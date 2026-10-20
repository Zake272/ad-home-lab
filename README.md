# Active Directory Home Lab

> Status: **in progress**. This repo documents the build as I go, with screenshots from my own lab.

A small Windows domain built on my own PC in VirtualBox: one Windows Server domain controller and one Windows client joined to the domain. The goal is to practice the day to day AD work a help desk or SOC analyst touches, and to generate real security logs I can investigate.

---

## Lab layout

| Machine | OS | Role | IP |
|---|---|---|---|
| `DC01` | Windows Server 2022 (evaluation) | Domain controller, DNS, DHCP | `10.0.0.10` |
| `CLIENT01` | Windows 11 Enterprise (evaluation) | Domain joined workstation | DHCP |

- **Domain:** `lab.zackwillis.local`
- **Network:** VirtualBox NAT Network `LabNet` (`10.0.0.0/24`), so the lab can reach the internet for updates but stays isolated from my home network

---

## Build log

### 1. Host setup
- [ ] Install VirtualBox
- [ ] Download Windows Server 2022 and Windows 11 evaluation ISOs from the Microsoft Evaluation Center
- [ ] Create the `LabNet` NAT Network

### 2. Domain controller
- [ ] Create the `DC01` VM and install Windows Server 2022
- [ ] Set a static IP and rename the server
- [ ] Install AD DS and promote to a new forest
- [ ] Configure DNS and a DHCP scope

### 3. Directory structure
- [ ] Create OUs for departments (IT, HR, Sales) and a separate OU for workstations
- [ ] Create users and security groups with PowerShell from a CSV
- [ ] Delegate password reset rights on one OU to a help desk group

### 4. Client
- [ ] Create `CLIENT01`, install Windows 11, join the domain
- [ ] Sign in as a domain user and confirm Group Policy applies

### 5. Group Policy
- [ ] Password and account lockout policy
- [ ] Map a network drive by group
- [ ] Block Control Panel for standard users

### 6. Security and auditing
- [ ] Enable advanced audit policy for logon events
- [ ] Trigger failed logons and a lockout, then find Event IDs 4625 and 4740 in Event Viewer
- [ ] Write up the investigation like a ticket

---

## Help desk scenarios practiced

Common tickets, worked end to end in the lab. Each one gets a short writeup: the problem, how I found it, and the fix.

- Locked out account
- Forgotten password reset
- User added to the wrong group
- New hire onboarding and offboarding

---

## Skills shown

Windows Server, Active Directory Domain Services, DNS, DHCP, Group Policy, PowerShell, Windows event logs, VirtualBox

## Related

Builds on my Microsoft Applied Skills credential: **Administer Active Directory Domain Services**.
