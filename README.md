# Runelite-Stream-Commands
A bunch of useful commands you can use to plugin to wiki and runelite api's in order to augment your stream.


## Sus Command
Shows noteable features of an osrs account in a condensed way.

<p>
<image align="center" src="https://github.com/LogicsSoldier/Runelite-Stream-Commands/assets/4423284/261d6b17-dbd7-4d37-b9ac-4ca60302a26d" width="400" height="120">
</image>
</p>

Features
 - total level / combat level
 - is iron / type
 - top 3 interesting non99s
 - show high agility lvls / inferno / colosseum
 - favorite activity
   
-------

<details>
  <summary>Nightbot</summary>

  ```
  !addcom !sus /me $(urlfetch https://script.google.com/macros/s/AKfycbx6Hk9ANAvbWJ4RTSZIXQeAlT4aMZcvZQ_ujvMBWHvY15r9paYTbCvpQkCRCXEQBLFi/exec?raw=$(querystring))
  ```

</details>
<details>
  <summary>StreamElements</summary>
  
  ```
  !command add !sus /me $(urlfetch https://script.google.com/macros/s/AKfycbx6Hk9ANAvbWJ4RTSZIXQeAlT4aMZcvZQ_ujvMBWHvY15r9paYTbCvpQkCRCXEQBLFi/exec?raw=${queryescape ${1:}})
  ```

</details>
<details>
  <summary>Botrix</summary>
  
  ```
  !addcom !sus fetch[https://script.google.com/macros/s/AKfycbx6Hk9ANAvbWJ4RTSZIXQeAlT4aMZcvZQ_ujvMBWHvY15r9paYTbCvpQkCRCXEQBLFi/exec?raw=$(variable)]
  ```

</details>
