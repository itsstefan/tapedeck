# tapedeck

## idea

I'd like to have a little web-frontend where I can plan {daily|weekly|etc...} recordings for radio shows (=mp3 streams) and issue youtube-dl-to-mp3 conversions. It would also be cool to have certain youtube channels subscribed and youtube-dl-to-mp3-converted automatically. 

Everything should land as mp3 files on the file system in a folder structure like (do I want some/more metadata in extra files, embed in files?):

```
store
+-- 2020
  +-- ...
+-- 2021
  +-- ...
+-- 2022
    +-- 01
    +-- 02
    +-- 03
        +-- 01
        +-- ...
        +-- 29
        +-- 30
            +--- 2022_03_30_P_vlc_OE1_Evening_Journal.mp3
            +--- 2022_03_30_P_vlc_OE1_Some_Show.mp3
            +--- 2022_03_30_A_ydl_http_some_fake_url.mp3
```

This file system structure should also be presented via the web-frontend for streaming - maybe in a very lightweight UI just like muxtape had.

Intended to run on a little vserver somewhere in the cloud; for one household.

## requirements

ahhh, i don't know yet

## implementation

* I think i'll try to use gunicorn as WSGI server
     * small rest api to issue commands, edit the shedule, list files in store. what do i need for streaming?
     * utilize 'captain' module to enqueue commands
     * litte backend/daemon that 1.) listen/executes captain commands, 2.) executes commands to fullfill the shedule
* dont' know if i need werkzeug or flask
* mmmh, i liked svelte a while ago but i probably don't need it
* mmmh, i liked tailwindcss a while ago but i probably don't need it

