Courtly
=======
A web implementation of the popular card game _Love Letter_.
![Art by Connie Lim](http://i.imgur.com/IpVia2y.jpg?1 "Decked Out: Fashion Playing Cards by Connie Lim")

Planning
--------
- flask app
- responds to any URL
- stateless, takes list of commands and generates current board

Schema
------
### Action Types
- seed
- setup
- play card
    - select player
- select card (on prompt)

### In
```yaml
user_id: "str"
game_type:
    short_name: "str"
actions:
    - "action0"
    - "action1"
    - ...
```

### Out
```yaml
current player: "str"
board:
    current player: "str"
    players:
        - "player0":
            position: int
            hand:
                - "card1"
                - "card2"
            discard_pile:
                - "card3"
                - "card4"
                - ...
        - "player1":
            position: int
            hand:
                - "hidden"
                - "hidden"
            discard_pile:
                - "card5"
                - "card6"
                - ...
        - ...
    last_action:
        (some abstraction of last action for replay/summary/prompt view)
```
