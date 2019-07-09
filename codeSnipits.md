return a user including its players
~~~
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
~~~
return a player including its user and room
~~~
Player.findByPk(playerId, { include: [User, Room] })
{
  id
  user: {
    id
    name
    pw
    playerIds
  }
  room: {
    id
    cards
  }
}
~~~
When you create a user:
`User.create`

When a user joins a room
~~~~
User.find(user =>
  Player.create({ user })
)
~~~~