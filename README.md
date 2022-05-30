# EscapeMania
The first Escape Room within Trackmania!

# How to run a game

Unfortunately, it's a bit of an involved setup. Should take you about 10 minutes. It works either on Windows or Linux.

## Setting up the files

* Download TrackmaniaServer http://files.v04.maniaplanet.com/server/TrackmaniaServer_Latest.zip
* Unzip it in a folder called `TrackmaniaServer/`
* Download all the files in this repo
* Move them in `TrackmaniaServer/UserData/` such that the following file exists: `TrackmaniaServer/UserData/Maps/EscapeMania by Vjeux & Ze-Rax.Map.Gbx`


## (Optional) Setting up admin commands

* Go to https://trackmania.io/
* Login with your Ubisoft account
* <img width="431" alt="image" src="https://user-images.githubusercontent.com/197597/170896262-705be3db-ab1a-4d45-9dac-768129053ec6.png">
* Copy your Login
* Update the following file with your Login: https://github.com/escapemania/escapemania/blob/b10e92266415a7a7358d424b6f425a72ebef2f5d/Scripts/Modes/Trackmania/EscapeMania.Script.txt#L48


## Setting up server authentication

* Go to https://players.trackmania.com/server/dedicated/create
* Find some non-used name for the server, it will be used as login and submit
* <img width="612" alt="image" src="https://user-images.githubusercontent.com/197597/170897024-71086328-e95a-4557-a86f-5b3bfba62d34.png">
* You should get a big red looking dialog like this:
* <img width="520" alt="image" src="https://user-images.githubusercontent.com/197597/170897093-f7930447-347c-47fd-9d88-8c555d0c54a7.png">
* Update the following two lines with the login (the name you put as server) and password (the big scary red line)
https://github.com/escapemania/escapemania/blob/b09c402c83cb2db829c1a14b13fd0861a9ce6b48/Config/dedicated_cfg.txt#L5-L6


## Setting up the Room in Club

* Go to Trackmania and chose the `Club` menu
* <img width="823" alt="image" src="https://user-images.githubusercontent.com/197597/170897180-b3126fdb-2271-40d4-96dc-fea5459384f2.png">
* Chose a Club or create a new one
* Click the `+` on the right
* <img width="1611" alt="image" src="https://user-images.githubusercontent.com/197597/170897219-5114b3d0-b60f-4ef0-8cf7-d20aaa6e1aeb.png">
* Select `Room`
* <img width="740" alt="image" src="https://user-images.githubusercontent.com/197597/170897247-30ae515a-ce19-4be9-bb98-91268991d6f9.png">
* Select `Use your dedicated server`
* <img width="1356" alt="image" src="https://user-images.githubusercontent.com/197597/170897270-54a70c17-cc1f-450f-9c65-fba50cc98bac.png">
* Add a room name at the top and select the dedicated server login you created above. Then click on `Create Room`
* <img width="1033" alt="image" src="https://user-images.githubusercontent.com/197597/170897299-502c00ef-22a0-4c33-84b6-fa6f010facf4.png">

## Starting the server

Run the following command:

```
./TrackmaniaServer /nodaemon /title=Trackmania /dedicated_cfg=dedicated_cfg.txt /game_settings=MatchSettings/EscapeMania.txt
```

If you are on Windows, you need to add `.exe` at the end of `TrackmaniaServer`

If you want to run it in the background, remove `/nodaemon`. Note that you won't see if there are errors starting the server. If you are on linux and want to kill the existing instance first, you can run: `pkill -f TrackmaniaServer`.

## Joining the room

Once the server is started, have the 4 players go to your club, click on the room and press `Join Room`. Enjoy!

