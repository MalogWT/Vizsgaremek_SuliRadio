## TODO
> [!IMPORTANT]
> Automating adding/playing song via links will be hard to create, only try if we have time to spare.
> Adding songs automatically is not avaliable when not using links, only show to admin side.

- Database (users, music)
  - Keep track of users:
    - email
    - password
    - votes
  - keep track of music:
    - music file/link
    - music metadata
    - current ratings (good/bad)
  - keep track of ongoing votes
    - discard time
    - votes (good/bad)

- program (c# or other)
  - console app
  - Manage music playing
    - read music based on database
      - read if file
      - wizard magic if link*
    - shuffle music based on config
    - play music

  - handle users
    - differentiate between login and sign in
      - (login) see if credentials match with existing account
      - (sign in) add user to database if credentials don't already exist

  - Handle voting
    - see if voting, autopass and autodiscard is enabled
    - manage incoming votes
      - add to database
      - remove from database
    - see if votes surpassed autopass limit
      - manage music accordingly
    - see if ongoing votes surpassed discard time
      - discard from database if so
     
  - Edit config
    - accessable through web interface, console or config file
    - check if passwords needed
      - if so, check if its corrent
    - allow chaning of the following
      - password (password/disable)
      - music
        - type? (link/files)
        - add folder/file/link
          - add to database and store location
        - shuffle? (enable/disable)
      - voting
        - avaliable? (enable/disable)
        - autopass? (allow automatic handling of votes if enabled)
        - autodiscard? (allow automatic discarding of ongoing votes if goals not reached within time)
        - vote limit (amount of votes needed for autopass)
        - discard time (amount of time alloted for voting before discard)
        - handle current ongoing votes (grand/deny)

- Web interface
  - user side
    - list of all songs in current music pool
    - current playing song
      - metadata and remaning time
    - login to enable rating/voting feature
      - choose to login or sign in
    - voting feature
    - current ongoing votes
      - show operation (add/remove), votes, song and time left (if applicable)
  - Admin side
    - only accessable through backend (console)
    - show condensed list of songs and current one playing
    - show all config options
    - allow easy editing of songs (adding, removing, changing order)
    - allow changing of config options
