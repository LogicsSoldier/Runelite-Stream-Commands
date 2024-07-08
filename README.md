# Runelite-Stream-Commands
A bunch of useful stream bot commands you can use to lookup OSRS related information and augment your stream. No installation.

![Static Badge](https://img.shields.io/badge/No_Additional_Permissions_Needed-Moderators_Can_Add-green)
![Static Badge](https://img.shields.io/badge/Safe_Secure-No_Identifiable_Information_Accessed-blue)
![Static Badge](https://img.shields.io/badge/Protected_Through_Separation_Of_Concerns-purple)

#### Commands
 - **!sus**   [Account Lookup](#sus-command)
 - **!price**   [Item Prices](#price-command)
 - **!wlink**   [Quick Wiki Page](#wiki-link-command)

#### Explanation
> These commands use google scripts and the native bots built for the streaming platforms you love. This keeps your IP and information hidden and allows the scripts to be platform independent.

#### Installation
> It's as easy as finding the command you want, selecting which bot your using (nightbot, streamelements, or botrix), and copy pasting that command into your chat.

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
  !addcom !price /me $(urlfetch https://script.google.com/macros/s/AKfycbyYtxnCW7oND6bMs8faGK57CKHg0qqK5DuHPrrOr2Hg9r6TiJOuZ5bV9kwi61j3D4-y/exec?raw=$(querystring))
  ```

</details>
<details>
  <summary>StreamElements</summary>
  
  ```
  !command add !price /me $(urlfetch https://script.google.com/macros/s/AKfycbyYtxnCW7oND6bMs8faGK57CKHg0qqK5DuHPrrOr2Hg9r6TiJOuZ5bV9kwi61j3D4-y/exec?raw=${queryescape ${1:}})
  ```

</details>
<details>
  <summary>Botrix (Kick.com)</summary>
  
  ```
  !addcom !price fetch[https://script.google.com/macros/s/AKfycbyYtxnCW7oND6bMs8faGK57CKHg0qqK5DuHPrrOr2Hg9r6TiJOuZ5bV9kwi61j3D4-y/exec?raw=$(variable)]
  ```

</details>


