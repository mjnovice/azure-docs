---
title: Users and groups in Conditional Access policy - Azure Active Directory
description: Who are users and groups in an Azure AD Conditional Access policy

services: active-directory
ms.service: active-directory
ms.subservice: conditional-access
ms.topic: conceptual
ms.date: 03/17/2021

ms.author: joflore
author: MicrosoftGuyJFlo
manager: karenhoran
ms.reviewer: calebb

ms.collection: M365-identity-device-management
---
# Conditional Access: Users and groups

A Conditional Access policy must include a user assignment as one of the signals in the decision process. Users can be included or excluded from Conditional Access policies. Azure Active Directory evaluates all policies and ensures that all requirements are met before granting access to the user. 

> [!VIDEO https://www.youtube.com/embed/5DsW1hB3Jqs]

## Include users

This list of users typically includes all of the users an organization is targeting in a Conditional Access policy. 

The following options are available to include when creating a Conditional Access policy.

- None
   - No users selected
- All users
   - All users that exist in the directory including B2B guests.
- Select users and groups
   - All guest and external users
      - This selection includes any B2B guests and external users including any user with the `user type` attribute set to `guest`. This selection also applies to any external user signed-in from a different organization like a Cloud Solution Provider (CSP). 
   - Directory roles
      - Allows administrators to select specific built-in Azure AD directory roles used to determine policy assignment. For example, organizations may create a more restrictive policy on users assigned the global administrator role. Other role types are not supported, including administrative unit-scoped roles and custom roles.
   - Users and groups
      - Allows targeting of specific sets of users. For example, organizations can select a group that contains all members of the HR department when an HR app is selected as the cloud app. A group can be any type of user group in Azure AD, including dynamic or assigned security and distribution groups. Policy will be applied to nested users and groups.

> [!IMPORTANT]
> When selecting which users and groups are included in a Conditional Access Policy, there is a limit to the number of individual users that can be added directly to a Conditional Access policy. If there are a large amount of individual users that are needed to be added to directly to a Conditional Access policy, we recommend placing the users in a group, and assigning the group to the Conditional Access policy instead.

> [!WARNING]
> If users or groups are a member of over 2048 groups their access may be blocked. This limit applies to both direct and nested group membership.

> [!WARNING]
> Conditional Access policies do not support users assigned a directory role [scoped to an administrative unit](../roles/admin-units-assign-roles.md) or directory roles scoped directly to an object, like through [custom roles](../roles/custom-create.md).

## Exclude users

When organizations both include and exclude a user or group the user or group is excluded from the policy, as an exclude action overrides an include in policy. Exclusions are commonly used for emergency access or break-glass accounts. More information about emergency access accounts and why they are important can be found in the following articles: 

* [Manage emergency access accounts in Azure AD](../roles/security-emergency-access.md)
* [Create a resilient access control management strategy with Azure Active Directory](../authentication/concept-resilient-controls.md)

The following options are available to exclude when creating a Conditional Access policy.

- All guest and external users
   - This selection includes any B2B guests and external users including any user with the `user type` attribute set to `guest`. This selection also applies to any external user signed-in from a different organization like a Cloud Solution Provider (CSP). 
- Directory roles
   - Allows administrators to select specific Azure AD directory roles used to determine assignment. For example, organizations may create a more restrictive policy on users assigned the global administrator role.
- Users and groups
   - Allows targeting of specific sets of users. For example, organizations can select a group that contains all members of the HR department when an HR app is selected as the cloud app. A group can be any type of group in Azure AD, including dynamic or assigned security and distribution groups.

### Preventing administrator lockout

To prevent an administrator from locking themselves out of their directory when creating a policy applied to **All users** and **All apps**, they will see the following warning.

> Don't lock yourself out! We recommend applying a policy to a small set of users first to verify it behaves as expected. We also recommend excluding at least one administrator from this policy. This ensures that you still have access and can update a policy if a change is required. Please review the affected users and apps.

By default the policy will provide an option to exclude the current user from the policy, but this default can be overridden by the administrator as shown in the following image. 

![Warning, don't lock yourself out!](./media/concept-conditional-access-users-groups/conditional-access-users-and-groups-lockout-warning.png)

If you do find yourself locked out[What to do if you are locked out of the Azure portal?](troubleshoot-conditional-access.md#what-to-do-if-you-are-locked-out-of-the-azure-portal)

## Next steps

- [Conditional Access: Cloud apps or actions](concept-conditional-access-cloud-apps.md)

- [Conditional Access common policies](concept-conditional-access-policy-common.md)
