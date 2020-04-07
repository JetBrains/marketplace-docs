[//]: # (title: Organizations)

## Overview

The number of plugins on the Marketplace is constantly growing. These plugins are created by both individual users and companies. To simplify the search process and the support of plugins, and also to increase the credibility of plugins, we have added a new entity – **_Organizations_**.
An organization lets you gather on a single page such company-wide information as company website and email address. An organization includes both plugin authors and their plugins. Each organization has a name and a *unique ID*.

## Rules

1. Registered users can [create organizations](https://plugins.jetbrains.com/organizations/new).
2. The user who created the organization becomes its *administrator*.
3. The organization's administrator can [add new members](##-Add-a-member) to the organization.
4. The organization's administrator can grant additional administrator roles to other members of the organization.
5. Organization members can [transfer their plugins](##-Plugin-transfer) to the organization.
6. A plugin can be transferred to an organization if and only if the vendor field in the plugin descriptor is the same as the organization ID.
7. If a plugin is transferred to the organization:
    1. The plugin authors retain the right to manage their plugins, even if some of them do not belong to the organization.
    2. The plugin can additionally be managed by the organization's administrators.
    3. The vendor field in the plugin descriptor should be the same as the organization ID.
8. The organization can have only one ID. Multiple IDs are not allowed.
9. Paid plugins must belong to an organization. It is necessary to associate the organization with the Company/Author's Full Legal Name, which is used in the Sales System.
10. An organization can be [verified](##-Verified-organizations) by JetBrains.

## Verified organizations

"Verified organizations" have proved their commitment to the JetBrains platform and are considered to be a reliable plugin vendor. If an organization would like to be marked as "Verified", one of its members should contact the JetBrains Plugins Repository support and request this.

## Examples

The ID of the organization [JetBrains s.r.o.](https://plugins.jetbrains.com/organization/JetBrains) is "JetBrains". To be able to transfer a plugin to this organization, the organization's administrator or the author of the plugin should configure the plugin as described below.

### IntelliJ IDEA-based IDEs

* A plugin with `<vendor>JetBrains</vendor>` may be transferred to the JetBrains organization.
* A plugin with `<vendor>JetBrains s.r.o</vendor>` may not be transferred to the JetBrains organization.

### TeamCity

* A plugin must have `<vendor><name>JetBrains</name></vendor>` in order to be transferred to the JetBrains organization.

### ReSharper

* A NuGet package must have an ID such as `JetBrains.<something>`, as described in the [docs](https://www.jetbrains.com/help/resharper/sdk/HowTo/Start/CreateNuGetPackageForPlugin.html), to be transferred to the JetBrains organization.

### Hub

* A widget must have JetBrains as the author to be transferred to the JetBrains organization.

## Add a member

To add more members, an organization's administrator should open the organization edit page [https://plugins.jetbrains.com/organization/{&organization_unique_id}/edit](https://plugins.jetbrains.com/organization/{&organization_id}/edit), switch to the "People & Plugins" tab, and enter the plugin author's ID in the "Add User" field.

## Plugin transfer

In order to transfer a plugin to an organization, a member should:
1. Specify the organization's unique ID in the plugin.xml file as described in the [Examples](##-Examples).
2. Click the **Transfer** button on the plugin edit page.