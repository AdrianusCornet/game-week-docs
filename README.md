a colaberation betwean
- [Ionut Sirbu](https://www.linkedin.com/in/isirbu)
- [Andrew Omajuwa](https://www.linkedin.com/in/andrew-omajuwa)
- [Adrianus Cornet](linkedin.com/in/adrianus-cornet-27390a172)

# The Game: Black Jack 

#### [Client](https://github.com/AdrianusCornet/game-week-client)
#### [Server](https://github.com/AdrianusCornet/game-week-server)

## Database schema

User
- id
- name
- hashed password
- players = a array of player id's (User.hasMany(Player))
- ? credits

Player
- id
- user = a user id `Player.belongsTo(User)`
- room = a room id `Player.belongsTo(Room)`
- cards
- ? bet

Room
- id
- cards house
- status
- players `Room.hasMany(User)`
- ? name
- ? room password

## Properties in the redux store
- user
    - name
    - jwt
- games = a array of objects representing a game
    - game = a object containing data about a game
        - id
        - house
            - cards = a array of cards
        - players = a array of player objects
            - player
                - id
                - name
                - cards = a array of cards
                - ? bet

## Handled routes

### get
- /rooms
- /rooms/:id
- /users
- /users/:id
- /ping

### post (subscribe)
- /rooms (returns a list of rooms whidt minimal extra data)
- /rooms/:id (returns all the data consurnign a room)
- ? /user/:id (returns the credists of a user)

### post
- /submit
- /login
- /draw
- /hold
- ? bet options
- /leaveTable

### put
- ? /user/:id

### delete
- ? /user/:id

## Files structure

### client

standard react file structure
- components/
  - RoomList/
    - RoomListContainer.jsx
    - RoomListDisplay.jsx

### server

same as in exercises

## legend
? = optional