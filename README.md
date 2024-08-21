# Runelite-Stream-Commands
A bunch of useful stream bot commands you can use to lookup OSRS related information and augment your stream. No installation.

![Static Badge](https://img.shields.io/badge/No_Additional_Permissions_Needed-Moderators_Can_Add-green)
![Static Badge](https://img.shields.io/badge/Safe_Secure-No_Identifiable_Information_Accessed-blue)
![Static Badge](https://img.shields.io/badge/Protected_Through_Separation_Of_Concerns-purple)

#### Recommended Commands
 - **!sus**   [Account Lookup / Identifier](#sus-command-player-lookup)
 - **!price**   [Realtime Item Prices](#price-command)
 - **!news**   [Finds Latest Blog Post](#latest-blog-post-news-command)
 - **!wlink**   [Quick & Safe Wiki Link Generation For Streams](#wiki-link-command)

#

##### Neat but niche:
   - **!item**   [Quick Attribute Retrieval](#item-stats)
   - **!wiki**   [Advanced Wiki Text Search](#wiki-text-query)
   - **!maxhit**   [Maxhit Calculator w/ Prefabs](#max-hit-calculator-w-prefabs)

##### Requires configuration:
 - **!kc + !lvl**   [Streamer Kc/Lvl Command](#streamer-lvlkc-commands)

#
   
#### Explanation
> These commands use google scripts and the native bots built for the streaming platforms you love. This keeps your IP and information hidden and allows the scripts to be platform independent.

#### Installation
> It's as easy as finding the command you want, selecting which bot you're using (nightbot, streamelements, or botrix), and copy pasting that command into your chat.

<br/>

<details>
 
 <summary><i>... for nerds who want even more information on how the command functions</i></summary>
 
<br/>

<br/>

![image](https://github.com/user-attachments/assets/63ad7d26-dd62-4910-8f55-64b47198930a)

.. lack of artistic skill aside

<br/>

>Now that it's saved, anytime a user calls the command the bot can use the command referenced to send a GET request to the google script's url! It works like any independent webpage the bot can query. Your favorite chatbot already watches your chat for commands. When a user types a command these bots are natively able to pick up the text and send it to a url, in this case a google script, using the url reference in the command. The google script then performs it's calculations internally before sending back to the bot to post in chat. The user never actually interacts with the google script protecting their IP. Only the bot (nightbot, streamelements, or botrix) interacts or is exposed to the script. The bot reads their message directly from chat like anyone else.

> I think it's unquestionable this makes it much safer than simply even browsing a website yourself since the streambot operates as an external proxy for the user, additionally the text returned in this format has no ability to influence or call other commands, both per the common sense rules implemented by each one of these stream bots and as an extra precaution by the /me prefaced in the commands when available. =D



</details>

----


#### Youtube Guide

[![Video Explanation](https://img.youtube.com/vi/ikNUu3j78Xw/0.jpg)](https://www.youtube.com/watch?v=ikNUu3j78Xw)


#### Credits
Streamers: [Bellis](https://www.twitch.tv/bellis), [Westham](https://www.twitch.tv/westham), [Vanc](https://www.twitch.tv/Vanc), [Osku](https://www.twitch.tv/Osku), and [Dino_xx](https://www.twitch.tv/dino_xx)

Honorable mentions: [jay_gravy](https://www.twitch.tv/jay_gravy), [scriptkid_rs](https://www.twitch.tv/scriptkid_rs), and many others who showed love and chatted with me in discord.

_Special thanks to these streamers for inspiring me to make this in the first place / letting me test these commands in their streams. All lovely fellows. ALSO, huge thanks to wiki boys for making such widely available API's and assisting when there were server issues._


----

<br/>

## Sus Command (Player Lookup)
Shows noteable features of an osrs account in a condensed format.

<p>
<image align="center" src="https://github.com/LogicsSoldier/Runelite-Stream-Commands/assets/4423284/261d6b17-dbd7-4d37-b9ac-4ca60302a26d" width="400" height="120">
</image>
</p>

#### Features
 - shows total level / combat level
 - is iron / type
 - top 3 "interesting" combat levels that aren't 99 (if applicable).
 - important account achievements (I.E. high agility lvls / inferno / colosseum)
 - favorite activity (highest ranked)
   
-------

| Copy & Paste An Option Below |
| --- | 

<br/>

> [!TIP]
> StreamElements is the preferred choice as it allows for multiple requests to be queued at once.

<br/>

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

<br/>

## Price Command
Looks up real time prices accurate up to 5 minutes.

<p>
<image align="center" src="https://github.com/LogicsSoldier/Runelite-Stream-Commands/assets/4423284/3156c7cf-a63e-4d58-8f19-2b4fe0249fbc" width="400" height="105">
</image>
</p>

#### Features
 - Uses Runelite's API to get real time prices with similar accuracy to GE tracker and other services
 - Multiple levels of name resolvers so you always find what your looking for
 - Allows for virtual sets such as torva set (which doesnt exist) to be calculated as a bulk query
 - a very simple trending feature so you can see which way the tides are turning
   
-------

| Copy & Paste An Option Below |
| --- | 

<br/>

> [!TIP]
> StreamElements is the preferred choice as it allows for multiple requests to be queued at once.

<br/>

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

<br/>

## Latest Blog Post (News Command)
Super simple command. No inputs required. Scrapes osrs website for latest update blog post.


<p>
<image align="center" src="https://github.com/LogicsSoldier/Runelite-Stream-Commands/assets/4423284/e3f7fc78-42bf-4765-8bb0-164f4025c354" width="400" height="130">
</image>
</p>
<p>

#### Features
 - Links to the latest Jagex update blog, and that's it =)
   
-------

| Copy & Paste An Option Below |
| --- | 

<br/>

> [!TIP]
> StreamElements is the preferred choice as it allows for multiple requests to be queued at once.

<br/>

<details>
  <summary>Nightbot</summary>

  ```
  !addcom !news $(urlfetch https://script.google.com/macros/s/AKfycbxzSsJ0bh5LH0TfJ2IBHGt7odD4tTQWKZ1uhxVBc1GyvtumBIAUA5SOijg1XHc2yLBA/exec)
  ```

</details>
<details>
  <summary>StreamElements</summary>
  
  ```
  !command add !news $(urlfetch https://script.google.com/macros/s/AKfycbxzSsJ0bh5LH0TfJ2IBHGt7odD4tTQWKZ1uhxVBc1GyvtumBIAUA5SOijg1XHc2yLBA/exec)
  ```

</details>
<details>
  <summary>Botrix (Kick.com)</summary>
  
  ```
  !addcom !news fetch[https://script.google.com/macros/s/AKfycbxzSsJ0bh5LH0TfJ2IBHGt7odD4tTQWKZ1uhxVBc1GyvtumBIAUA5SOijg1XHc2yLBA/exec]
  ```

</details>


<br/>

## Wiki Link Command
Uses the same wiki resolver implemented in the price command to rapidly find **oldschool.runescape.wiki** links for the chat. These links are always trusted and safe.

<p>
<image align="center" src="https://github.com/LogicsSoldier/Runelite-Stream-Commands/assets/4423284/5aa7362f-d326-4453-a8d8-1eb7b7821658" width="400" height="120">
</image>
</p>

#### Features
 - Uses wiki resolver for flexible querying
 - Quickly displays related wiki links in chat
 - Easy way to allow for trusted links
   
-------

| Copy & Paste An Option Below |
| --- | 

<br/>

> [!TIP]
> StreamElements is the preferred choice as it allows for multiple requests to be queued at once.

<br/>

<details>
  <summary>Nightbot</summary>

  ```
  !addcom !wlink /me $(urlfetch https://script.google.com/macros/s/AKfycbyGaYevqufPqXbFUUCbulDCm0Yl-p0OzMAMdIghOKc7PLdTUs63XaxdyjfjHBn3CtuX/exec?raw=$(querystring))
  ```

</details>
<details>
  <summary>StreamElements</summary>
  
  ```
  !command add !wlink /me $(urlfetch https://script.google.com/macros/s/AKfycbyGaYevqufPqXbFUUCbulDCm0Yl-p0OzMAMdIghOKc7PLdTUs63XaxdyjfjHBn3CtuX/exec?raw=${queryescape ${1:}})
  ```

</details>
<details>
  <summary>Botrix (Kick.com)</summary>
  
  ```
  !addcom !wlink fetch[https://script.google.com/macros/s/AKfycbyGaYevqufPqXbFUUCbulDCm0Yl-p0OzMAMdIghOKc7PLdTUs63XaxdyjfjHBn3CtuX/exec?raw=$(variable)]
  ```

</details>

<br/>

## Item Stats
Pulls up the item statbox from the wiki

<p>
<image align="center" src="https://github.com/user-attachments/assets/9931f95e-e587-4c8c-b8a9-8a1ae31c595c" width="400" height="100">
</image>
</p>

#### Features
 - Uses wiki resolver for flexible querying
 - Quickly display items offensive and defensive values
 - filters out unnecessary values
   
-------

| Copy & Paste An Option Below |
| --- | 

<br/>

> [!TIP]
> StreamElements is the preferred choice as it allows for multiple requests to be queued at once.

<br/>

<details>
  <summary>Nightbot</summary>

  ```
  !addcom !item /me $(urlfetch https://script.google.com/macros/s/AKfycbz0mzMK_sW5vw5mfAU3qHuNOUimNtJRTSXtHPO6IDEgJyUf7kr1aa8oWr2sJu8aWudolQ/exec?raw=$(querystring))
  ```

</details>
<details>
  <summary>StreamElements</summary>
  
  ```
  !command add !item /me $(urlfetch https://script.google.com/macros/s/AKfycbz0mzMK_sW5vw5mfAU3qHuNOUimNtJRTSXtHPO6IDEgJyUf7kr1aa8oWr2sJu8aWudolQ/exec?raw=${queryescape ${1:}})
  ```

</details>
<details>
  <summary>Botrix (Kick.com)</summary>
  
  ```
  !addcom !item fetch[https://script.google.com/macros/s/AKfycbz0mzMK_sW5vw5mfAU3qHuNOUimNtJRTSXtHPO6IDEgJyUf7kr1aa8oWr2sJu8aWudolQ/exec?raw=$(variable)]
  ```

</details>

<br/>

## Wiki Text Query
Pretty advanced wiki query command. Attempts to get the information you need and present it neatly.

<p>
<image align="center" src="https://github.com/LogicsSoldier/Runelite-Stream-Commands/assets/4423284/073c8a39-fcf6-4549-b110-9b5ba26271cb" width="400" height="240">
</image>
</p>

#### Syntax
`!wiki <subject>`

`!wiki <subject> | <sub-query>` 

`!wiki <subject> | <sub-query> [increments]` 

EXAMPLE: `!wiki dwarf | pickaxe <<` 

  -- *returns the second to last pickaxe reference on the page about dwarves*

`|` allows you to perform a text search within the page you find

if you perform a sub query you can also do:

`>` increment, forward from start of page

`<` decrement, move backwards from the end of the page


#### Features
 - Quickly calculate max hit potential based on any styles current strength
 - save prefabs and armor sets for later use
 - Can modify player levels, passives, pot boosts etc
   
-------

| Copy & Paste An Option Below |
| --- | 

<br/>

> [!TIP]
> StreamElements is the preferred choice as it allows for multiple requests to be queued at once.

<br/>

<details>
  <summary>Nightbot</summary>

  ```
  !addcom !wiki /me $(urlfetch https://script.google.com/macros/s/AKfycbybRK2W3RkjbhCDEKhB0oUt-Pn5Oz5Om32UmXUSGitWYBGFUzF8t1jNU3oS_Z4Ln5tX4Q/exec?raw=$(querystring))
  ```

</details>
<details>
  <summary>StreamElements</summary>
  
  ```
  !command add !wiki /me $(urlfetch https://script.google.com/macros/s/AKfycbybRK2W3RkjbhCDEKhB0oUt-Pn5Oz5Om32UmXUSGitWYBGFUzF8t1jNU3oS_Z4Ln5tX4Q/exec?raw=${queryescape ${1:}})
  ```

</details>
<details>
  <summary>Botrix (Kick.com)</summary>
  
  ```
  !addcom !wiki fetch[https://script.google.com/macros/s/AKfycbybRK2W3RkjbhCDEKhB0oUt-Pn5Oz5Om32UmXUSGitWYBGFUzF8t1jNU3oS_Z4Ln5tX4Q/exec?raw=$(variable)]
  ```

</details>

<br/>

## Max Hit Calculator w/ Prefabs
This one is really complicated and probably needs more explanation on how to use it but it's a max hit calculator that works as a command.

<p>
<image align="center" src="https://github.com/LogicsSoldier/Runelite-Stream-Commands/assets/4423284/ee67b346-0c5e-464b-b0a1-4dfa87ae75a8" width="400" height="95">
</image>
</p>
<p>
<image align="center" src="https://github.com/LogicsSoldier/Runelite-Stream-Commands/assets/4423284/34690d9a-4736-4914-b7c4-9aaa052a10df" width="400" height="140">
</image>
</p>

> [!WARNING]
> Due to my lack of willpower to document this command, A LOT of it's features remain hidden.

#### Syntax

##### Basic 
 - `!maxhit <optional name OR list of prefabs?> --<range|melee|mage>=<style specific strength value>`
 - with prefab `!maxhit ags -m` OR with just str value `!maxhit -m=132`
 - can also be combined so `!maxhit ags -m=53` would give you the value while wearing certain jewelry too
 - `!maxhit ags+bandos+jewelry -m` is a great way to combine prefabs

##### Options
 - `--pot` = current increase by strength pot (defaults to max for style)
 - `--prayer` = current percentage increase by prayer this will default to augury / rigour / piety if no value is provided
 - `--tomb` = forces tome of fire on or off. by default it'll detect fire spells and assume tome use.
 - `--elysian` = max hit if elysian procs
 - `--salve`
 - `--slayer`
 - `--isPraying`


#### Features
 - Quickly calculate max hit potential based on any styles current strength
 - save prefabs and armor sets for later use
 - Can modify player levels, passives, pot boosts etc

###### additional information
If you'd like to read through my tests to see some of it's potential [check here](https://github.com/LogicsSoldier/Runelite-Stream-Commands/assets/4423284/ecc13020-5879-4aca-b71e-e2caf5f5fe7d)

-------

| Copy & Paste An Option Below |
| --- | 

<br/>

> [!TIP]
> StreamElements is the preferred choice as it allows for multiple requests to be queued at once.

<br/>

<details>
  <summary>Nightbot</summary>

  ```
  !addcom !maxhit /me $(urlfetch https://script.google.com/macros/s/AKfycbwHwHFdR4s8H1SjRN70bUIpu-LOIqEG7i9w1iyUL4cZqN-HR3kKMZibECSjKi1N1o_PoQ/exec?raw=$(querystring))
  ```

</details>
<details>
  <summary>StreamElements</summary>
  
  ```
  !command add !maxhit /me $(urlfetch https://script.google.com/macros/s/AKfycbwHwHFdR4s8H1SjRN70bUIpu-LOIqEG7i9w1iyUL4cZqN-HR3kKMZibECSjKi1N1o_PoQ/exec?raw=${queryescape ${1:}})
  ```

</details>
<details>
  <summary>Botrix (Kick.com)</summary>
  
  ```
  !addcom !maxhit fetch[https://script.google.com/macros/s/AKfycbwHwHFdR4s8H1SjRN70bUIpu-LOIqEG7i9w1iyUL4cZqN-HR3kKMZibECSjKi1N1o_PoQ/exec?raw=$(variable)]
  ```

</details>

<br/>

----- 

#### Configuration Required For All Commands Below

<br/>

>[!NOTE]
> Manual Configuration Section ( For the experienced dev )

<h6> 

 The commands below all require manual configuration, and may require more experience to set up.

 You should understand this before continuing
 
 </h6>

 | name | example |
 | -- | -- |
 | base url | https://script.google.com/macros/s/AKfycbyU8LGlB05uSKoBOePVu1pZu8i72N3eZA9LTZ1uB1icq-i7i11dyFK0RJVS0QilxMfL/exec |
 | start of url params | ? |
 | param name | streamer |
 | equal operator | = |
 | argument | b0aty |
 | and operator | & |
 
 
 
 Example: `?streamer=b0aty&raw=$(querystring)`



<br/>

## Streamer Lvl+Kc Commands
Searches for a level or task with kc depending on configuration

<img src="https://github.com/LogicsSoldier/Runelite-Stream-Commands/assets/4423284/7769a713-61d7-4787-9f13-11b6c33e15e0" width="400" height="230"></img>

> [!NOTE]
> This command requires you to configure.

###### URL

```
https://script.google.com/macros/s/AKfycbyU8LGlB05uSKoBOePVu1pZu8i72N3eZA9LTZ1uB1icq-i7i11dyFK0RJVS0QilxMfL/exec
```

###### URL Components

| name | description |
| --- | --- |
| streamer | `string` osrs account for the streamer |
| isLvl | `true\|false` determines if lvl or kc command |
| raw | `string` this will be the value to search for normally a good place for the querystring |


###### Example 

Url + `?streamer=b0aty&isLvl=false&raw=Overall` 

