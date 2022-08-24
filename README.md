# easy-pms-apis

Listed below are the APIs that are ready for the mobile apps based on specifications received. 

### NB: APIs are currently connected to a free temporal and unstable database. For correct testing environment and results they would need to connected to permanent database.

### APIs can be tested with postman and it likes.

URL for server is: 
```
http://easy-apis-pneumono.herokuapp.com
```

#### Register a user authorization to call apis
```
POST /users/token/client/new
```
- Takes req.body.name as String, req.body.uid as String and req.body.role('driver'/'rider') as String
- Returns a bearer token that must be used in all subsequent requests headers

#### Get the authorization token for an already registered user
```
GET /users/token/:uid
```
- Takes uid of user used in registration
- Returns a bearer token that must be used in all subsequent requests

#### Get last N points earned by user
```
GET /users/points/:uid/:limit
```
- Takes uid of user and N number of events to return
- Returns an object containing events, their points and timestamp for the user


#### Award events points when triggered by user
```
POST /users/new
```
- Takes userid: req.body.uid as String, req.body.timestamp as timestamp, event name: req.body.name as String, special event: req.body.special_event as String.
- Pass special event if event triggers a special event.
- Returns an object containing events, their points and timestamp for the user




