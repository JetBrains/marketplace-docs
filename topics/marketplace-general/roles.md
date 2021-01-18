[//]: # (title: Roles)

People could have various roles in JetBrains Marketplace.
The roles provided in order from less permissive. Each next role has all the permissions of the previous one.

## Non-registered user
A user who is not logged in with the [JetBrains Hub](https://hub.jetbrains.com/) account.
### Permissions
* Read-only access to the Marketplace catalog (can see plugins pages, download available plugin versions)

## Registered user
A user who is logged in with the JetBrains Hub account.
### Permissions
* Upload new plugins
* Write reviews/comments
* Rate plugins
* Create [organizations](https://plugins.jetbrains.com/docs/marketplace/organizations.html)

## Plugin Author
A user who is added as a Developer to at least one plugin.
### Permissions
* Publish updates for their plugins
* Add new authors to their plugins
* Edit the information of their plugins
* Add [custom pages](https://plugins.jetbrains.com/docs/marketplace/custom-pages.html) to their plugins
* Move their plugins to an organization if they are members of this organization and the plugins are properly configured
* Check statistics of their plugins
* Apply their plugins to be [sold](https://plugins.jetbrains.com/docs/marketplace/submit-a-request-to-sell-plugins-at-the-marketplace.html) on the Marketplace
* Subscribe to the new comments/reviews of their plugins
* Subscribe to the verification results of their plugins (if available)

## Organization administrator
Global administrator in the scope of an organization.
### Permissions
* Manage organization details
* Manage organization staff
* Manage organization plugins
* Grant other organization members the administrator role
* Remove the organization (only if this organization doesn’t have vendor information for paid plugins)

## Moderator
This role is needed for specific JetBrains team members to provide an ability to manage plugins in the scope of a family. As of now, we have the following moderator types:
* IntelliJ-based IDEs
* TeamCity
* Hub
* .Net

### Permissions
Manage all plugins of a specific type (edit the information of these plugins, approve/unapprove these plugins and/or their updates, remove them).

## Marketplace administrator
The role with global rights for members of the JetBrains Marketplace team.
### Permissions
* All
