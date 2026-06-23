# Active Directory User Onboarding Lab

![Status](https://img.shields.io/badge/Project-Completed-success)
![Active Directory](https://img.shields.io/badge/Directory-Active%20Directory-0078D4)
![Onboarding](https://img.shields.io/badge/Focus-User%20Onboarding-2F6FED)

A completed Active Directory lab in which I created and configured a new domain user, assigned group-based access, prepared a home folder and validated first sign-in from a domain-joined Windows client.

> **Status:** Completed and validated. This repository documents work already performed in a private lab. Real names, usernames, departments, groups, paths and credentials have been generalized.

## Objectives completed

- Created a structured user account in Active Directory
- Applied naming and account standards
- Added the user to role-based security groups
- Configured a home-folder path
- Applied access through existing share and NTFS permissions
- Tested first sign-in on a domain client
- Verified group membership and effective access
- Tested password-change behavior
- Documented onboarding findings

## Implementation summary

1. Confirmed the correct OU and naming convention for the new user.
2. Created the Active Directory account with controlled initial settings.
3. Added the user to the required role-based groups.
4. Configured the home-folder path and drive mapping.
5. Verified that the target folder and permissions were created correctly.
6. Signed in on a domain-joined Windows client.
7. Changed the initial password where required.
8. Tested access to approved resources and denial from unauthorized resources.
9. Reviewed the account attributes and group memberships after validation.

## Validation commands

```powershell
Get-ADUser <user> -Properties *
Get-ADPrincipalGroupMembership <user> | Select-Object Name
Get-ADUser <user> -Properties HomeDirectory, HomeDrive
```

```cmd
whoami
whoami /groups
net use
```

## Outcome

The new user successfully authenticated to the domain, received the intended group-based access and could use the assigned home-folder resource. Access outside the approved role remained restricted.

## Findings

- Group-based access was more scalable and auditable than assigning permissions directly to the individual account.
- Correct OU placement mattered because user-targeted Group Policy and delegated administration followed the directory structure.
- A successful account creation did not prove onboarding was complete; sign-in, password change, drive mapping and resource access all required validation.
- Group-membership changes sometimes required a fresh logon token before the updated permissions became visible.
- Consistent naming and attribute standards improved searchability and reduced administrative mistakes.
- Testing denied access was as important as testing successful access because it confirmed least privilege.

## Skills demonstrated

- Active Directory user administration
- OU placement and naming standards
- Security-group assignment
- Home-folder configuration
- SMB and NTFS access validation
- Domain sign-in testing
- Least-privilege onboarding
- Technical documentation

## Security notes

- No real user identity or credential is included.
- All names, groups and paths are placeholders or generalized.
- The lab was completed in a controlled non-production environment.

## Author

**Dewald Pretorius** — L2 IT Support Engineer
