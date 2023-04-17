## Search for songs

<p style='border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;'>
The next part of your script will use the playlist length your user requests, to search for music that fits your class. It will keep searching until it finds the number of songs on the database which fit your user’s requested playlist.
</p>

Logically, you want the app to keep on searching for songs that fit, until the playlist is the length requested by the user.

--- task ---

Add a `repeat until < >`{:class="block3control"} block from the golden `Control`{:class="block3control"} menu to your script:

```blocks3
when this sprite clicked
delete all of [playlist v]
ask [How many songs would you like?] and wait
set [length v] to (answer)
ask [What genre would you like?] and wait
set [length v] to (answer)
repeat until ()
```

--- /task ---

--- task ---

From the green `Operators`{:class="block3operators"} menu, place a gem-shaped `( ) = (50)`{:class="block3operators"} block into the gem shaped hole in the repeat until block:

```blocks3
when this sprite clicked
delete all of [playlist v]
ask [How many songs would you like?] and wait
set [length v] to (answer)
ask [What genre would you like?] and wait
set [length v] to (answer)
repeat until [] =[50])
```

--- /task ---

--- task ---

From the orange List menu, add a `length of [Playlist]`{:class="block3variables"} block into the first hole of the green operator block:

```blocks3
when this sprite clicked
delete all of [playlist v]
ask [How many songs would you like?] and wait
set [length v] to (answer)
ask [What genre would you like?] and wait
set [length v] to (answer)
repeat until ((length of [Playlist v])=[50])
```

--- /task ---

--- task ---

From the orange `Variables`{:class="block3variables"} menu, add a length bubble to the second hole of the green operator block:

```blocks3
when this sprite clicked
delete all of [playlist v]
ask [How many songs would you like?] and wait
set [length v] to (answer)
ask [What genre would you like?] and wait
set [length v] to (answer)
repeat until ((length of [Playlist v])=(length))
```
This will make a loop that repeats until the Playlist is the length your user defined earlier.

--- /task ---

--- task ---

The next thing you need your application to do is search for a random song on the music database to compare to your model.

Add a `random song from genre( )`{:class="block3flag"} block from the green `Spotify`{:class="block3flag"} menu to your new loop:

```blocks3
when this sprite clicked
delete all of [playlist v]
ask [How many songs would you like?] and wait
set [length v] to (answer)
ask [What genre would you like?] and wait
set [length v] to (answer)
repeat until ((length of [Playlist v])=(length))
random song from genre [] :: #338854
```

--- /task ---

--- task ---

Add an orange `genre`{:class="block3variables"} bubble from the `Variables`{:class="block3variables"} menu to the green `random song`{:class="block3flag"} block:


```blocks3
when this sprite clicked
delete all of [playlist v]
ask [How many songs would you like?] and wait
set [length v] to (answer)
ask [What genre would you like?] and wait
set [genre v] to (answer)
repeat until ((length of [Playlist v])=(length))
random song from genre (genre) :: #338854
```


--- /task ---

Now that your script has returned a song from the genre your user chose, the song needs to be compared against your model to determine if it fits their preferences for the playlist they want. If it doesn’t fit, it won’t be added and the application should search again.


