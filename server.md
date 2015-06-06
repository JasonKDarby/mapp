#server
In general, services should be as stateless as possible, which is likely entirely.  
Each of the services should be implemented separately from each other.

The services include [authentication](server.md#authentication), [users](server.md#users), [user groups](server.md#user-groups), [locations](server.md#locations), and [location groups](server.md#location-groups). 

##### authentication
I would rather use external authentication systems than have to manage security at that level.  This service should be able to tie one or more external identities to create/update users.  It should provide a session id that can be used across the other services.

##### users
A user should be associated with one or more external identities.  For as long as possible I want to avoid having more user information than a name.  A user:
* can be a member of a group
* can create a group
* is able to CRUD locations
* is able to CRUD groups of locations
* can copy visible locations

##### user groups
A group of users is primarily for having controlled access to locations.
A user group:
* belongs to an owner.  The owner can control location visibility, add locations to a group and remove locations from a group.
* has members.  Group members have location visibility regardless of external visibility.
* is able to CRUD locations
* is able to CRUD groups of locations

##### locations
Locations are the primary content of the app.
A location:
* can belong to a user
* can belong to a group
* can belong to a group of locations
* consists of a name and coordinates
* has visibility which is based on it's own list and inherited from the group of locations it belongs to

##### location groups
A location group:
* can belong to a user
* can belong to a group
* can belong to a group of locations
* consists of a name, coordinates, a collection of locations, and a collection of groups of locations
* has visibility which is based on it's own list and inherited from the group of locations it belongs to

Solutions that I'd rather not implement within this project include:
* solutions for using a generated session id, and possibly also managing it's generation
* logging that goes to a common (preferably external) service
* permissions
