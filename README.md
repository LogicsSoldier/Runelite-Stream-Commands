# Runelite-Stream-Commands
A bunch of useful stream bot commands you can use to lookup OSRS related information and augment your stream. No installation.

![Static Badge](https://img.shields.io/badge/No_Additional_Permissions_Needed-Moderators_Can_Add-green)
![Static Badge](https://img.shields.io/badge/Safe_Secure-No_Identifiable_Information_Accessed-blue)
![Static Badge](https://img.shields.io/badge/Protected_Through_Separation_Of_Concerns-purple)

#### Commands (recommended)
 - **!sus**   [Account Lookup](#sus-command)
 - **!price**   [Item Prices](#price-command)
 - **!wlink**   [Quick Wiki Page](#wiki-link-command)

#### Neat but less professional / more advanced
 - **!wiki**   [Wiki Text Queries](#wiki-text-query)
 - **!maxhit**   [Maxhit Calculator](#max-hit-calculator-w-prefabs)

#### Explanation
> These commands use google scripts and the native bots built for the streaming platforms you love. This keeps your IP and information hidden and allows the scripts to be platform independent.

#### Installation
> It's as easy as finding the command you want, selecting which bot your using (nightbot, streamelements, or botrix), and copy pasting that command into your chat.

#### Credits
Streamers: [Bellis](https://www.twitch.tv/bellis), [Westham](https://www.twitch.tv/westham), [Vanc](https://www.twitch.tv/Vanc), [Osku](https://www.twitch.tv/Osku), and [Dino_xx](https://www.twitch.tv/dino_xx)

_Special thanks to these streamers for inspiring me to make this in the first place / letting me test these commands in their streams. All lovely fellows. ALSO, huge thanks to wiki boys for making such widely available API's and assisting when there were server issues._

## Sus Command
Shows noteable features of an osrs account in a condensed way.

<p>
<image align="center" src="https://github.com/LogicsSoldier/Runelite-Stream-Commands/assets/4423284/261d6b17-dbd7-4d37-b9ac-4ca60302a26d" width="400" height="120">
</image>
</p>

Features
 - shows total level / combat level
 - is iron / type
 - top 3 interesting non99s
 - important account achievements (I.E. high agility lvls / inferno / colosseum)
 - favorite activity (highest ranked)
   
-------

> [!TIP]
> StreamElements is the preferred choice as it allows for multiple requests to be queued at once.

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
  <summary>Botrix (Kick.com)</summary>
  
  ```
  !addcom !sus fetch[https://script.google.com/macros/s/AKfycbx6Hk9ANAvbWJ4RTSZIXQeAlT4aMZcvZQ_ujvMBWHvY15r9paYTbCvpQkCRCXEQBLFi/exec?raw=$(variable)]
  ```

</details>


## Price Command
Looks up real time prices accurate up to 5 minutes.

<p>
<image align="center" src="https://github.com/LogicsSoldier/Runelite-Stream-Commands/assets/4423284/3156c7cf-a63e-4d58-8f19-2b4fe0249fbc" width="400" height="105">
</image>
</p>

Features
 - Uses Runelite's API to get real time prices with similar accuracy to GE tracker and other services
 - Multiple levels of name resolvers so you always find what your looking for
 - Allows for virtual sets such as torva set (which doesnt exist) to be calculated as a bulk query
 - a very simple trending feature so you can see which way the tides are turning
   
-------

> [!TIP]
> StreamElements is the preferred choice as it allows for multiple requests to be queued at once.


<details>
  <summary>Nightbot</summary>

  ```
  !addcom !price /me $(urlfetch https://script.google.com/macros/s/AKfycbxgDKb-yxuAdbJFOVPETNUC3e2Mnhm92DO-6eVDEsYT5YRgtxZXxoGitmB89Lc5YCtF/exec?raw=$(querystring))
  ```

</details>
<details>
  <summary>StreamElements</summary>
  
  ```
  !command add !price /me $(urlfetch https://script.google.com/macros/s/AKfycbxgDKb-yxuAdbJFOVPETNUC3e2Mnhm92DO-6eVDEsYT5YRgtxZXxoGitmB89Lc5YCtF/exec?raw=${queryescape ${1:}})
  ```

</details>
<details>
  <summary>Botrix (Kick.com)</summary>
  
  ```
  !addcom !price fetch[https://script.google.com/macros/s/AKfycbxgDKb-yxuAdbJFOVPETNUC3e2Mnhm92DO-6eVDEsYT5YRgtxZXxoGitmB89Lc5YCtF/exec?raw=$(variable)]
  ```

</details>

## Wiki Link Command
Uses the wiki resolver also used by the price command to rapidly pull up a link in chat.

<p>
<image align="center" src="https://github.com/LogicsSoldier/Runelite-Stream-Commands/assets/4423284/5aa7362f-d326-4453-a8d8-1eb7b7821658" width="400" height="120">
</image>
</p>

Features
 - Uses wiki resolver for flexible querying
 - Quickly displays related wiki links in chat
   
-------

> [!TIP]
> StreamElements is the preferred choice as it allows for multiple requests to be queued at once.


<details>
  <summary>Nightbot</summary>

  ```
  !addcom !wlink /me $(urlfetch https://script.google.com/macros/s/AKfycbyYtxnCW7oND6bMs8faGK57CKHg0qqK5DuHPrrOr2Hg9r6TiJOuZ5bV9kwi61j3D4-y/exec?raw=$(querystring))
  ```

</details>
<details>
  <summary>StreamElements</summary>
  
  ```
  !command add !wlink /me $(urlfetch https://script.google.com/macros/s/AKfycbyYtxnCW7oND6bMs8faGK57CKHg0qqK5DuHPrrOr2Hg9r6TiJOuZ5bV9kwi61j3D4-y/exec?raw=${queryescape ${1:}})
  ```

</details>
<details>
  <summary>Botrix (Kick.com)</summary>
  
  ```
  !addcom !wlink fetch[https://script.google.com/macros/s/AKfycbyYtxnCW7oND6bMs8faGK57CKHg0qqK5DuHPrrOr2Hg9r6TiJOuZ5bV9kwi61j3D4-y/exec?raw=$(variable)]
  ```

</details>



## Max Hit Calculator w/ Prefabs
This one is really complicated and probably needs more explanation on how to use it but it's a max hit calculator that works as a command.

<p>
<image align="center" src="https://github.com/LogicsSoldier/Runelite-Stream-Commands/assets/4423284/ee67b346-0c5e-464b-b0a1-4dfa87ae75a8" width="400" height="95">
</image>
</p>
<p>
<image align="center" src="https://github.com/LogicsSoldier/Runelite-Stream-Commands/assets/4423284/34690d9a-4736-4914-b7c4-9aaa052a10df" width="400" height="125">
</image>
</p>

Features
 - Quickly calculate max hit potential based on any styles current strength
 - save prefabs and armor sets for later use
 - Can modify player levels, passives, pot boosts etc
   
-------

> [!TIP]
> StreamElements is the preferred choice as it allows for multiple requests to be queued at once.


<details>
  <summary>Nightbot</summary>

  ```
  !addcom !maxhit /me $(urlfetch https://script.google.com/macros/s/AKfycbybRK2W3RkjbhCDEKhB0oUt-Pn5Oz5Om32UmXUSGitWYBGFUzF8t1jNU3oS_Z4Ln5tX4Q/exec?raw=$(querystring))
  ```

</details>
<details>
  <summary>StreamElements</summary>
  
  ```
  !command add !maxhit /me $(urlfetch https://script.google.com/macros/s/AKfycbybRK2W3RkjbhCDEKhB0oUt-Pn5Oz5Om32UmXUSGitWYBGFUzF8t1jNU3oS_Z4Ln5tX4Q/exec?raw=${queryescape ${1:}})
  ```

</details>
<details>
  <summary>Botrix (Kick.com)</summary>
  
  ```
  !addcom !maxhit fetch[https://script.google.com/macros/s/AKfycbybRK2W3RkjbhCDEKhB0oUt-Pn5Oz5Om32UmXUSGitWYBGFUzF8t1jNU3oS_Z4Ln5tX4Q/exec?raw=$(variable)]
  ```

</details>


## Wiki Text Query
Pretty advanced wiki query command. Attempts to get the information you need and present it neatly.

<p>
<image align="center" src="https://github.com/LogicsSoldier/Runelite-Stream-Commands/assets/4423284/073c8a39-fcf6-4549-b110-9b5ba26271cb" width="400" height="215">
</image>
</p>

#### Syntax
`!wiki <subject>`

`!wiki <subject> | <sub-query>` (example: !wiki dwarf | pickaxe)

`|` allows you to perform a text search within the page you find

if you perform a sub query you can also do

`>` increment, forward from start of page

`<` decrement, move backwards from the end of the page


Features
 - Quickly calculate max hit potential based on any styles current strength
 - save prefabs and armor sets for later use
 - Can modify player levels, passives, pot boosts etc
   
-------

> [!TIP]
> StreamElements is the preferred choice as it allows for multiple requests to be queued at once.


<details>
  <summary>Nightbot</summary>

  ```
  !addcom !maxhit /me $(urlfetch https://script.google.com/macros/s/AKfycbybRK2W3RkjbhCDEKhB0oUt-Pn5Oz5Om32UmXUSGitWYBGFUzF8t1jNU3oS_Z4Ln5tX4Q/exec?raw=$(querystring))
  ```

</details>
<details>
  <summary>StreamElements</summary>
  
  ```
  !command add !maxhit /me $(urlfetch https://script.google.com/macros/s/AKfycbybRK2W3RkjbhCDEKhB0oUt-Pn5Oz5Om32UmXUSGitWYBGFUzF8t1jNU3oS_Z4Ln5tX4Q/exec?raw=${queryescape ${1:}})
  ```

</details>
<details>
  <summary>Botrix (Kick.com)</summary>
  
  ```
  !addcom !maxhit fetch[https://script.google.com/macros/s/AKfycbybRK2W3RkjbhCDEKhB0oUt-Pn5Oz5Om32UmXUSGitWYBGFUzF8t1jNU3oS_Z4Ln5tX4Q/exec?raw=$(variable)]
  ```

</details>
