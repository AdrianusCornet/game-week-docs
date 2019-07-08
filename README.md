# The Game: Black Jack 

#### url client repo: ...
#### url server repo: ...

##  Database schema

Users
- id
- name
- hashed password
- players (User.hasMany(Player))
- ? credits

User.findAll({ include: [Player] })
[
  {
    id
    name
    pw
    players: [{
      id
      userId
      roomId
      cards
    }]
  }
]

Players
- id
- user (Player.belongsTo(User))
- room (Player.belongsTo(Room))
- cards
- (bet)

Player.findByPk(playerId, { include: [User, Room] })
{
  id
  user: {
    id: 3,
    name
    pw
    playerIds
  }
  room: {
    id
    cards
  }
}

When you create a user:
  User.create

When a user joins a room
  User.find(user =>
    Player.create({ user })
  )

Rooms
- id
- ? name
- ? room password
- cards house
- status
- players (has many players)

## 3. What properties will the redux store have?
- user
  - name
  - jwt
- games = a array of objects representing a game
  - game = a object containing data about a game
    - id
    - players = a array of all players includign the hous in the room
    - carts = a 2d array of the carts in the room (a 1d array per player)

##### (this is stil t.b.d.)

## 4. What routes will be handled?

get
- /rooms
- /rooms/:id
- /users
- /users/:id
- /ping

post (subscribe)
- /rooms
- /rooms/:id
- ? /user/:id

post
- /submit
- /login
- /draw
- /hold
- ? bet options
- /leaveTable

put
- ? /user/:id

delete
- ? /user/:id

## 5. How will the files be structured

### client

standard react file structure
components/
  RoomList/
    ContainerRoomList.jsx // index.jsx???
    DisplayRoomList.jsx

### server

same as in exercises

## legend
? = optinal