##Concept
I'm thinking of an app that would provide a map with user generated points of interest.  The major draw would be collections of POIs, things like:
* fishing spots around a lake
* kiosks and stores in a mall
* offices, entrances, exits in a building
* vendors and sections in a theater
* sections in a store
* dynamic positions like a person's location

with various groupings for permissions and availability.

###narrative examples

  I'm going to a wine festival with Bob and Alice.  We all have the app and are affiliated with each other personally so we can broadcast our locations to each other since we'll likely split up.  Also, we have each stored the locations provided by the wine festival so we know where there are particular vendors we want to visit.  When we get there, I store the location of the party bus pick up and send it to my friends.  I create a group including the 3 of us and we go in separate directions. The wine I went to was not very good so I ask my friends' locations.  Bob shows up on my map immediately, his location is set to share with me automatically.  Alice sends a notification showing her current location.

  Andy goes to recover a tree stand he set up previously.  He sees the location and plans a route, staying clear of the place on the way where he scouted deer and marked a POI weeks earlier.

  Pizza Delivery Guy just started at a new pizzeria, luckily they have already set up a number of the regular customers' addresses as POIs for him.

  Developer is working on an app to generate grocery lists with extra information.  Developer sure is happy that they can access store layout information through the Mapplication API.

##Implementation considerations

Locations should be easy to generate which probably means entering an address, using a user's current location, or pointing to a spot on a map.

The domain model probably contains:
* locations
* groups of locations
* users
* user groups
* location/group ownership and visibility on user and user group levels

The server and each of the platform clients should probably be considered different projects.

##Out of scope

Groups of points to define complex location boundaries.

Ideally user management could be borrowed or integrated with another system, but a full implementation might be necessary.
