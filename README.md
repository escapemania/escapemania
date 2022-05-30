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


# How to develop locally

This is way simpler as you don't need a server or any authentication.

## Setup the map and files

* Download all the files in this repository and extract them on `Documents\Trackmania`. Such that this file exists `C:\Users\vjeux\OneDrive\Documents\Trackmania\Scripts\Modes\Trackmania\EscapeMania.Script.txt` (note that this is using my account `vjeux`).
* Edit the map as usual in the Trackmania editor.

## Run with scripts

* Instead of clicking the `Validate the track` button, in order to run with the script, you need to click on `Map Options`
* <img width="309" alt="image" src="https://user-images.githubusercontent.com/197597/170897843-37ff522c-5a20-4237-984f-45364af4620e.png">
* Select `Test the map with mode`
* <img width="629" alt="image" src="https://user-images.githubusercontent.com/197597/170897892-0eb5db32-0c54-41d1-b008-f6ffab48383b.png">
* Select `Trackmania`
* <img width="567" alt="image" src="https://user-images.githubusercontent.com/197597/170897926-fd513302-846b-41dd-afd5-fbce274d7c65.png">
* Select `EscapeMania.Script.txt`
* <img width="568" alt="image" src="https://user-images.githubusercontent.com/197597/170897940-e8bb2efd-a697-45f3-b987-6b254eb2285f.png">
* Click `Open`

## Edit the code

Now you are in the game with the script running!

Weirdly enough, in order to edit the code, you need to be running the script and pressing `Screen Lock` button on your keyboard.

* <img width="800" alt="image" src="https://user-images.githubusercontent.com/197597/170898011-43a800bb-4a53-4609-a30d-47352cd74027.png">
* You can edit code on the left, see files and errors on the right.
* If you want to run the new version of the code, press `Reload` and `Play` buttons
* <img width="361" alt="image" src="https://user-images.githubusercontent.com/197597/170898060-984ad927-e2e5-4244-8222-6bf7d8c70ece.png">

## Useful Tips

Few things that are useful when programming in this environment:
* Use the `log()` function to print things.
* Press `Ctrl+G` in order to show the log menu
* <img width="827" alt="image" src="https://user-images.githubusercontent.com/197597/170898181-831e10b5-a1d2-4495-81d4-c9cf2d13e641.png">

Back in the editor, if you want to set a tag on a checkpoint
* Press `Edit Block Properties`
* <img width="502" alt="image" src="https://user-images.githubusercontent.com/197597/170898241-1743ec48-dae8-4920-946e-8d0ad4609cb3.png">
* It starts showing the tags on all the checkpoints
* <img width="500" alt="image" src="https://user-images.githubusercontent.com/197597/170898259-57d18c47-4b47-4bbd-89b6-fd0661f45a8a.png">
* Click on a checkpoint to edit its tag
* <img width="488" alt="image" src="https://user-images.githubusercontent.com/197597/170898315-3cece5d2-a3e6-401b-9b65-e16469c4cad5.png">

`Test Mode` doesn't work where you click enter and it puts your car anywhere you want unfortunately.
* But you can add a new spawn called `DevSpawn` to start from there.
* <img width="912" alt="image" src="https://user-images.githubusercontent.com/197597/170898459-74e0c8e2-f382-4e5e-93b8-182187757ca1.png">
