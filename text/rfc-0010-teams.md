# Zesty.io RFC 0010 - Teams

## Overview

Zesty currently allows for groups of Users to be given access to Instances through Companies. Company functionality, however, is very limited: Companies can only be created by staff Users and can be seen by all Users (regardless of if they are in the Company or not). This functionality will be augmented and redesigned as "Teams" in the new Accounts API. Users will be able to create and delete Teams, as well as invite other Users (by email) to join their Team. Users can be added or deleted from the Team by one of its admins. The Team will have a default Roles associated with it. Adding a Team to an Instance will grant all Users in that Team access to the Instance with the default Roles. Similarly, removing a Team from an Instance will remove all the team members' access to the Instance.

Teams will be interacted with in a few ways:
  - Creation of Teams
  - Inviting a User to a Team
  - Accepting/Declining/Cancelling a Team Invite
  - Adding a Team to an Instance
  - Removing a User from a Team
  - Removing a Team from an Instance
  - Deletion of Teams

All Team-based functionality will be displayed in a separate "Teams" or "My Teams" page.



### Creation of Teams

Any User will be able to create a Team (at which point the User becomes the Team's admin). 


### Inviting a User to a Team

The admins of a Team will be allowed to invite Users. The invitation will be done using the primary email address of the User to be invited. Users will be able to view their open Team Invites in the "Teams" page, and well as pending invites they have sent out. A User invited to a Team that has already been assigned to an Instance will be granted the same Roles as everyone else in their Team. Users may select whether the invitee will also be an admin on the Team.


### Adding a Team to an Instance

Teams may be added to an Instance, which gives all Users in that Instance the default Role associated with the Team. If a User has a Team-assigned Role on a given Instance, and they are part of a different Team that is added to the same Instance, their Role will not change.


### Accepting/Declining/Cancelling a Team Invite

Users who are invited to a Team have the option to accept or decline the invite. If they accept, they are added to the Team; if they decline, nothing happens. The admins of the Team 
may cancel the invite, at which point the invited User will no longer have the option to accept/decline.


### Removing a User from a Team

Users may be removed from a Team by a Team's admin. If a User is removed from a Team, they may be reinvited by an admin. Removing a User from a Team removes all their Roles which were Team-assigned. 


### Removing a Team from an Instance

An admin of a Team may remove it from an Instance if they are the Instance's owner or admin. Removing a Team from an Instance removes all Team-assigned Roles for every User in the Team. 


### Deletion of Teams

Only a Team's admin may delete a Team. If a Team is deleted, ALL Team-assigned Roles for its Users are removed.
