# Lab 01 — User Provisioning, Security Groups & RBAC

## Scenario
**Environment:** Healthcare — Ottawa General Hospital (simulated)
**Ticket:** 3 new staff members starting Monday. Set up accounts
with appropriate access. IT Coordinator must manage user accounts
without access to billing or Azure infrastructure.

## Objectives
- Create user accounts with accurate job titles and departments
- Organize users into security groups by role
- Apply RBAC following the principle of least privilege

## What I Did

### 1. User Provisioning
Created 3 accounts in Microsoft Entra ID:

| User | Title | Department |
|---|---|---|
| alice.martin | IT Coordinator | Information Technology |
| bob.dupont | Finance Analyst | Finance |
| claire.nguyen | HR Specialist | Human Resources |

### 2. Security Groups
| Group | Type | Members |
|---|---|---|
| GRP-OttawaGen-IT | Security (Assigned) | alice.martin |
| GRP-OttawaGen-AllStaff | Security (Assigned) | All 3 users |

### 3. RBAC — Least Privilege
Assigned **User Administrator** Entra ID role to Alice Martin.

**Why User Administrator and not Global Administrator:**
The ticket requires user account management only — not billing,
Azure resources, or security policies. User Administrator grants
exactly what is needed: create/modify users, reset passwords,
manage group membership. Anything more would violate least privilege.

**Important distinction:**
- Entra ID roles (User Administrator, Global Administrator) →
  control IDENTITY management: users, groups, licenses
- Azure RBAC roles (Owner, Contributor, Reader) →
  control RESOURCE access: VMs, networks, storage

## Key Concepts Learned
- Security groups vs Microsoft 365 groups
- Assigned vs Dynamic group membership
- Least privilege principle in identity administration
- Difference between Entra ID roles and Azure RBAC roles

## Real-World Connection
This scenario mirrors onboarding requests at Demand ITS MSP
where new client employees required accounts with department-
specific access. The same RBAC principles apply whether the
environment is healthcare, government, enterprise, or MSP.

## Screenshots
- 01-users-list.png
- 02-groups.png
- 03-allstaff-members.png
- 04-alice-role.png
