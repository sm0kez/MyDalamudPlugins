# 🌊 WaveKeeper

A Dalamud plugin for Final Fantasy XIV that automatically greets nearby players with emotes and replies when someone emotes at you.

<img width="360" height="2173" alt="image" src="https://github.com/user-attachments/assets/b36154f7-d939-4142-a2ae-8dae76120ed6" />


---

## ✨ Features

### Core Greeting
- **Auto-Greet** — Automatically sends an emote to nearby players when they enter range
- **Auto-Reply** — Detects when someone emotes at you and replies back
- **Mimic Mode** — Reply with the same emote someone used on you
- **Goodbye Emote** — Send a farewell emote when a friend leaves range
- **Emote Chain** — Execute multiple emotes in sequence with custom delays
- **Emote Randomizer** — Pick from a custom list of emotes randomly
- **Returning Greet** — Different emote for first encounter of the day vs. returning later

### Who to Greet
- **Friends Only Mode** — Limit greetings to your friends list
- **FC Members** — Optionally greet Free Company members
- **Party Members** — Optionally greet party members
- **Whitelist Mode** — Only greet a specific list of named players
- **Per-Player Emotes** — Assign specific emotes to specific friends
- **Sprout Greeting** — Special emote for new adventurers (sprouts)
- **Returner Greeting** — Special welcome-back emote for returners

### Smart Filters
- **AFK Filter** — Pause greets/replies when you're AFK, or ignore AFK players
- **Activity Filters** — Pause while mounted, crafting, gathering, or in combat
- **Cutscene/Loading Filter** — Pause during cutscenes and loading screens
- **Duty/Instance Filter** — Automatically disable in duties and instances
- **Zone Whitelist/Blacklist** — Enable or disable in specific zones
- **Level Range Filter** — Only greet players within a specific level range
- **Zone Warmup** — Delay greetings for X seconds after loading into a new zone
- **Re-Greet Cooldown** — Don't re-greet someone for X minutes if they leave/return

### Stats & Tracking
- **Daily Greet Counter** — Track how many players were greeted today
- **Most Greeted Friend** — Track the player you encounter most often
- **Session Stats** — View greets, replies, and goodbyes for current session
- **Greet History Window** — Scrollable log with timestamps of all interactions
- **Export to CSV** — Save history data to CSV files

### UI & Quality of Life
- **Compact Mode** — Small floating overlay showing status and counts
- **Profiles/Presets** — Save and switch between different settings profiles
- **DTR Bar Toggle** — Clickable icon on the server info bar for quick enable/disable
- **Custom Chat Prefix** — Change `[WaveKeeper]` to a custom string
- **Chat Color** — Set a custom color for chat notifications
- **Chat Toggle** — Option to completely hide all WaveKeeper messages

### Scheduling
- **Time-Based Activation** — Only active during specific hours of the day
- **Auto-Disable Timer** — Turn off automatically after X minutes of activity

---

## 📥 Installation

1. Open FFXIV and type `/xlsettings` in chat
2. Go to the **Experimental** tab
3. Scroll down to **Custom Plugin Repositories**
4. Copy the repo URL below and paste it into the empty box
5. Click the **+** button, then **Save and Close**
6. Open the Plugin Installer with `/xlplugins`
7. Search for **WaveKeeper** and click **Install**

**Repository URL:**
```
https://raw.githubusercontent.com/sm0kez/MyDalamudPlugins/main/pluginmaster.json
```

Type `/wavekeeper` to open the settings window.

---

## 🔧 How It Works

1. **Scanning** — WaveKeeper periodically scans for nearby players within your configured range
2. **Filtering** — Players are filtered based on your settings (friends, FC, party, whitelist, AFK status, level, etc.)
3. **Greeting** — When a valid player is detected, it queues a greeting with your configured delay
4. **Reply Detection** — Uses a game emote hook to detect when someone emotes directly at you
5. **Auto-Reply / Mimic** — If someone emotes at you, it automatically replies (or mimics their emote)
6. **Goodbye** — When a greeted player leaves range, optionally sends a goodbye emote
7. **Cleanup** — Players are removed from the greeted list when they leave the area

---

## 💬 Commands

| Command | Description |
|---------|-------------|
| `/wavekeeper` | Open settings window |
| `/wavekeeper stats` | Open stats window |
| `/wavekeeper compact` | Toggle compact overlay |

---

## 📊 Stats Window

Click the **Stats** button in the main window or use `/wavekeeper stats` to view:

- Session greets, replies, and goodbyes
- Total and daily greet counts
- Most greeted players
- Full history log with timestamps
- Export to CSV

---

## 🎯 Quick Toggle (DTR Bar)

WaveKeeper adds a clickable entry to the server info bar (DTR):

- **WK ●** = Active (click to disable)
- **WK ○** = Inactive (click to enable)

---

## ❓ Frequently Asked Questions

---

**Most asked Question : Even after clearing greets, It doesn't do anything!**
> If you stand still for too long, the AFK filters kick in. Just move a bit to re-activate the plugin. AFK filters can be toggled on and off.

---

**Q1: Why doesn't it greet everyone around me, only my friends?**
> The default mode is **Friends Only**. Open `/wavekeeper` → **General → Who to Greet** and switch the mode to **Everyone**. You can also choose **Whitelist Only** if you want to control exactly who gets greeted.

---

**Q2: How do I spam emotes on someone like Copycat/Right Back At You does?**
> Enable **Reply & Mimic → Mimic Mode**, then set the **Mimic Cooldown to 0 seconds and set the Queue Spacing to 0.** This removes all delays, allowing you to mirror every incoming emote instantly for a true spam effect.

---

**Q3: Someone waved at me but WaveKeeper didn't reply. Why?**
> Auto-Reply is **off by default**. Go to **Reply & Mimic → Auto-Reply** and enable it. Also check your greet mode — if you're on **Friends Only**, WaveKeeper will only reply to people on your friends list.

---

**Q4: It greeted someone once but never again even though they're still nearby. Why?**
> WaveKeeper keeps a greeted list per session and won't greet the same person twice. Click **Clear Greeted** at the top of the settings window to reset it, or simply change zones — the list clears automatically.

---

**Q5: How do I make it wait a few seconds before greeting someone?**
> Go to **General → Timing → Greet Delay** and set it to however many seconds you want. A value of 3–5 seconds feels natural and avoids greeting someone who's just passing through.

---

**Q6: How do I assign a specific emote to a specific friend?**
> Go to **Player Lists → Per-Player Emotes**, enter the player's exact name and the emote command (e.g. `/dote`), then click **Add**. That player will always receive that emote instead of your default one.

---

**Q7: How do I stop it from greeting people while I'm crafting, mounted, or in combat?**
> Go to **Filters** and tick the relevant checkboxes — **Mounted**, **Crafting**, **Gathering**, and **Combat** are all available. WaveKeeper will automatically pause whenever those states are active.

---

**Q8: How do I make it only work in specific zones like my FC house?**
> Go to **Filters → Zone Whitelist**, enable it, search for your zone by name, and click **+** to add it. WaveKeeper will only greet players while you're inside a whitelisted zone and stay silent everywhere else.

---

**Q9: People keep getting greeted the moment they appear. Can I add a warmup after zoning?**
> Yes — go to **Filters → Zone Warmup** and set a delay in seconds. WaveKeeper will wait that long after you load into a zone before it starts greeting anyone, avoiding spam on zone-in.

---

**Q10: How do I send a goodbye emote when someone walks away?**
> Go to **Goodbye**, enable it, and set your emote command. WaveKeeper will automatically send it when a player you've already greeted moves out of your configured range.

---

**Q11: How do I run multiple emotes in a row after greeting someone?**
> Go to **Emote Chain**, enable it, pick when it fires (**Proactive Only**, **Replies Only**, **All Greets**, or **Goodbye Only**), then add steps with a command, delay, and motion toggle. WaveKeeper fires them in order after the initial emote.

---

**Q12: How do I greet FC members and party members too, not just friends?**
> In **General → Who to Greet**, set the mode to **Everyone** — or keep **Friends Only** and additionally enable **FC Members** and **Party Members** toggles so those groups are included alongside friends.

---

**Q13: How do I use a special emote only for sprouts or returners?**
> Go to **Sprout & Returner**, enable **Greet Sprouts** and/or **Greet Returners**, then set the emote you want to use for each. WaveKeeper will automatically use those instead of your default emote when it detects one nearby.

---

**Q14: How do I quickly enable or disable WaveKeeper without opening the settings?**
> Click the **WK ●** / **WK ○** entry in your server info bar (DTR bar) at the top of the screen. It toggles WaveKeeper on and off instantly. You can also use the **Enable/Disable** button in the Compact overlay (`/wavekeeper compact`).

---

**Q15: How do I make WaveKeeper only run during certain hours, like when I'm usually online?**
> Go to **Time & Auto-Disable → Time-Based Activation**, enable it, and set your **Start Hour** and **End Hour**. WaveKeeper will enable and disable itself automatically based on your local system clock.

---

**Q16: How do I stop someone from being greeted without fully ignoring them?**
> Go to **Player Lists → Ignore List** and add their name. They'll be permanently skipped for all greets, replies, mimic, and goodbyes — without affecting anything else.

---

**Q17: How do I see who I've greeted the most and export my history?**
> Click **Stats** at the top of the settings window or type `/wavekeeper stats`. You'll see session stats, all-time totals, your most greeted players, and a full timestamped history log. Click **Export CSV** to save it to a file.

---

**Q18: I have different playstyles — RP, casual, AFK farming. Can I save separate configs?**
> Yes — go to **Profiles**, give your current setup a name and click **Save New**. Switch between profiles any time from the **Active** dropdown. Each profile stores all settings independently.

---

**Q19: How do I stop WaveKeeper from printing messages in chat every time it greets someone?**
> Go to **Chat & Sound → Chat Toggle** and disable chat notifications entirely. Alternatively, customize the **Chat Prefix** or **Chat Color** to make them less intrusive if you still want to see them.

---

**Q20: WaveKeeper greeted someone who just briefly ran past me. How do I avoid that?**
> Increase the **Greet Delay** under **General → Timing** so WaveKeeper waits before acting. If the player leaves range before the delay expires, the queued greet is automatically cancelled — so a longer delay naturally filters out passersby.

---

**Q21: Why are my emotes queued with a delay when I use Mimic/Copycat mode?**
> WaveKeeper uses a **Queue Spacing** system to avoid sending emotes too fast and hitting the game's chat rate limit. Go to **General → Timing → Queue Spacing** and set it to **0** for instant firing.

---

**Q22: Someone spammed emotes at me and now there's a huge backlog of queued emotes firing one by one. How do I stop it?**
> Click **Clear Greeted** at the top of the settings window — this also flushes the entire emote queue immediately. Alternatively, set a **Mimic Cooldown** (even just 2–3 seconds) to prevent the queue from building up in the first place.

---

**Q23: Can I use WaveKeeper alongside Copycat at the same time?**
> Technically yes, but it's not recommended. Both plugins hook into emote events and will both try to react to incoming emotes, causing **doubled replies** and queue conflicts. Pick one or the other for mimic/reply behaviour and disable that feature in whichever plugin you're not using for it.

---

**Q24: My emote fires but it targets the wrong person when multiple people are nearby. Why?**
> WaveKeeper targets the player it's replying to before firing the emote. However if your target changes between the time the emote is queued and when it actually fires (due to queue spacing delay), it may land on whoever you're currently targeting. Enable **Target Before Greeting** in **General** to make WaveKeeper always re-target the correct player right before each emote fires.

---

**Q25: The queue keeps firing even after I disabled WaveKeeper mid-session. Is that normal?**
> This was a known issue in earlier versions. In the current version, disabling WaveKeeper mid-session will **stop the queue from draining** immediately. Any already-queued emotes are held and won't fire until you re-enable it — or you can flush them instantly with **Clear Greeted**.

---

**Q26: What is the "Scan Interval" setting for?**
> This controls how often WaveKeeper checks your surroundings for new players. A lower value (e.g. 1s) is faster but heavier on performance; a higher value (e.g. 5s) is more efficient for busy areas.

---

**Q27: Can I increase the detection range beyond 50 yalms?**
> No. FFXIV only provides object data for players within a certain radius. 15-20 yalms is the recommended range for natural social interactions; 50 is the maximum reliable range.

---

**Q28: Why does my character keep turning around suddenly?**
> This happens if **Target Before Greeting** is enabled. WaveKeeper automatically targets the player it's about to greet to ensure the emote lands correctly. Disable this if you want to keep facing your original direction.

---

**Q29: Does WaveKeeper work in instanced duties?**
> Only if you disable the **Duty/Instance Filter**. By default, WaveKeeper pauses itself in duties to avoid distracting emotes during mechanics or combat.

---

**Q30: Can I set the queue spacing to 0 for instant emotes?**
> Yes. Setting **Queue Spacing to 0** is the key to removing all artificial delays between emotes. This is recommended for users who want "instant" reactions or maximum spam capability.

---

**Q31: How do I make WaveKeeper use emotes without text in the chat box?**
> Enable **Motion Only** under **General → Emote**. This adds the `motion` parameter to your commands, playing the animation while keeping the chat log clean.

---

**Q32: Will a "Per-Player Emote" override my "Sprout Greeting"?**
> Yes. Per-Player overrides are the highest priority. If you have a specific emote set for a friend, WaveKeeper will use that even if they are a sprout, returner, or FC member.

---

**Q33: How does the "Re-Greet Cooldown" work?**
> If someone leaves your range and comes back, WaveKeeper won't greet them again until the configured time (in minutes) has passed. This prevents spamming someone who is running back and forth.

---

**Q34: Can I change the [WaveKeeper] text that appears in my chat?**
> Yes. Go to **Chat → Chat Prefix** and type anything you like. Leaving it blank will remove the prefix entirely.

---

**Q35: What are "Chat Color IDs"?**
> These are the numeric codes used by FFXIV for UI text colors. Setting this to something other than 0 will color the WaveKeeper notifications in your chat log.

---

**Q36: What happens if I go AFK?**
> If **Pause When AFK** is enabled, WaveKeeper will stop all automated greeting until you move or perform an action again.

---

**Q37: Can I ignore other players who are AFK?**
> Yes. Enable **Filters → Ignore AFK Players**. WaveKeeper will skip anyone with the red AFK chair icon, so you don't waste emotes on people who aren't at their keyboard.

---

**Q38: Is there a way to quickly toggle the Compact overlay?**
> Yes. Use the command `/wavekeeper compact` to show or hide the small floating status window.

---

**Q39: Can I hide the icon in the server info (DTR) bar?**
> Yes. In the settings, you can toggle the **DTR Bar Toggle** off to remove the WK icon from your top UI bar.

---

**Q40: How many entries does the "Greet History" hold?**
> The history log keeps track of the last 500 interactions. Once it hits the limit, the oldest entries are deleted to save memory.

---

**Q41: Where are the exported CSV files saved?**
> They are saved in your Dalamud plugin configurations folder, usually: `%appdata%\XIVLauncher\pluginConfigs\WaveKeeper_history.csv`.

---

**Q42: What is the difference between "Save New" and "Overwrite" in Profiles?**
> **Save New** creates a completely new profile slot with your current settings. **Overwrite** updates the currently selected profile with any changes you've made.

---

**Q43: Will I lose my stats if I delete a profile?**
> No. Stats (like total greets and history) are global and stored separately from the individual configuration profiles.

---

**Q44: If I'm in "Friends Only" mode, will it still greet people on my Whitelist?**
> Yes. The Whitelist and Per-Player lists always override the general "Who to Greet" logic.

---

**Q45: Can I blacklist certain zones like Limsa Aetheryte?**
> Yes. Use **Filters → Zone Blacklist** to prevent WaveKeeper from ever firing in specific high-traffic areas while keeping it active everywhere else.

---

**Q46: Why is there a "Zone Warmup"?**
> This gives the game world and player list a few seconds to load properly when you zone in. It prevents WaveKeeper from instantly waving at 20 people at once before your screen even fades in.

---

**Q47: Why would I use the Level Range filter?**
> It's useful for RP or social events where you only want to interact with players of a certain level (e.g. "new players only" or "level 100 only").

---

**Q48: Does it greet people in Linkshells?**
> Currently, the plugin can't reliably detect Linkshell membership through the game's API without external data. This is being researched for a future update.

---

**Q49: Does the Combat Filter stop replies?**
> No. By default, activity filters (Combat, Mounted, etc.) only stop *proactive* greetings. Auto-replies and Mimicry will still fire unless you specifically toggle them off.

---

**Q50: What happens to the queue when I logout?**
> The emote queue is cleared instantly when you logout or change zones to prevent "leftover" emotes from firing unexpectedly later.

---

**Q51: Can I see a list of all commands?**
> Yes. Type `/wavekeeper` for settings, `/wavekeeper stats` for the history window, and `/wavekeeper compact` for the overlay.

---

**Q52: Are my daily stats reset at a specific time?**
> Daily stats reset at midnight based on your local system clock.

---

**Q53: Does WaveKeeper affect my frame rate (FPS)?**
> The performance impact is negligible. Scanning for players is a very light operation, and the plugin stays idle most of the time.

---

**Q54: Will this conflict with "Honorific" or other name-related plugins?**
> No. WaveKeeper reads player data directly from the game's object table and does not interfere with how other plugins display names or titles.

---

**Q55: How do I know if I'm on the latest version?**
> The Dalamud Plugin Installer (`/xlplugins`) will notify you of any updates. Always keep the plugin updated for the best compatibility with new FFXIV patches.

---

**Q56: Does WaveKeeper work on NPCs or Quest targets?**
> No. WaveKeeper is designed specifically to interact with other player characters. It ignores NPCs, vendors, and quest-related entities to keep your chat and animations focused on social interaction.

---

**Q57: Can I use custom macros in WaveKeeper?**
> WaveKeeper currently supports direct `/emote` commands and standard game slash commands. It doesn't trigger player-made macros directly, but you can achieve similar results using the **Emote Chain** feature to sequence multiple emotes.

---

**Q58: Does the "Zone Whitelist" support player-run housing?**
> Yes. If you are inside a housing ward or a specific house that has a unique zone ID recognized by the game, you can add it to the whitelist. Note that some apartments and small rooms share IDs.

---

**Q59: How do I backup my settings and player lists?**
> Your settings are stored in the `%appdata%\XIVLauncher\pluginConfigs\WaveKeeper.json` file. Copying this file to a safe location or another PC will preserve your profiles and lists.

---

**Q60: Why did my character target a Chocobo or Minion?**
> WaveKeeper filters for player characters, but if the game's targeting system is busy or if **Target Before Greeting** fires while your client is lagging, it might briefly snap to the nearest interactable object. Increasing **Scan Interval** slightly can help.

---

**Q61: Does WaveKeeper work in first-person view?**
> Yes. However, if **Target Before Greeting** is enabled, your camera will snap to face the player being greeted, which can be disorienting in first-person. Disable that setting for a smoother experience.

---

**Q62: Can I use WaveKeeper while playing with a controller?**
> Absolutely. WaveKeeper runs in the background and uses internal commands, so it doesn't matter if you're using a keyboard, mouse, or controller.

---

**Q63: Does the plugin work if FFXIV is running in the background?**
> Yes, as long as the game client is active and you are logged in. If you have "Mute when game is in background" enabled in FFXIV settings, you won't hear the notification sounds, but the emotes will still fire.

---

**Q64: Can I export just a specific player's history?**
> The CSV export saves the entire history log. You can then open the file in Excel or Google Sheets and filter by the "Player" column to see only the interactions for a specific person.

---

**Q65: Does WaveKeeper greet "hidden" players or GMs?**
> WaveKeeper only sees what the game's object table provides. If a GM is invisible or if a player is not yet loaded into your client's memory, WaveKeeper won't detect them.

---

**Q66: Can I change the color of the "WK" DTR icon?**
> Currently, the icon color is tied to the plugin's status (Active/Inactive). A future update may include UI customization for the DTR entry.

---

**Q67: What happens if I target someone manually while WaveKeeper is about to greet them?**
> If **Target Before Greeting** is enabled, WaveKeeper will override your current target to ensure the emote hits the right person. If disabled, it will fire the emote at your current manual target.

---

**Q68: Does the "Combat Filter" also stop mimics?**
> By default, filters like Combat or Mounted only pause *proactive* greetings. Auto-replies and Mimics will still fire unless you also enable **Pause Replies When AFK** or manually toggle them.

---

**Q69: Can I set a range smaller than 5 yalms?**
> Yes. You can slider the range down to 1 yalm, though this effectively means you'll only greet people you are practically standing on top of.

---

**Q70: Does WaveKeeper work in the Diadem or Eureka?**
> Yes. These are considered open-world "zones" rather than instanced duties, so WaveKeeper will function normally unless you have specific zone filters active.

---

**Q71: Can I use "Emote Randomizer" for the Goodbye emote?**
> Currently, the randomizer only applies to the main Greeting emote. We are looking into expanding randomization to replies and goodbyes in a future update.

---

**Q72: Is there a limit to how many players can be on the Whitelist or Ignore list?**
> There is no hard-coded limit. However, keeping thousands of names in these lists may slightly impact performance when scanning.

---

**Q73: Does WaveKeeper work with the "Mare Lamentorum" (Mare Synchronos) plugin?**
> Yes. WaveKeeper doesn't interact with character visual data, so it is fully compatible with Mare and other visual-modding plugins.

---

**Q74: How do I reset everything to factory defaults?**
> You can delete the `WaveKeeper.json` file in your pluginConfigs folder while the game is closed. The plugin will regenerate a fresh default config the next time it loads.

---

**Q75: Does WaveKeeper affect my character's "Away" or "Online" status?**
> No. WaveKeeper only sends emotes and changes your target; it doesn't modify your social status or presence settings in the game.

---

**Q76: Does WaveKeeper work with different client languages (JP/DE/FR)?**
> Yes. WaveKeeper is language-agnostic as it uses internal IDs and standard slash commands that are translated by the game client automatically.

---

**Q77: Does it greet Cross-World visitors (Wanderers/Travelers)?**
> Yes. If they are in your range and meet your filter criteria (e.g. Mode set to "Everyone"), WaveKeeper will greet them regardless of their home world.

---

**Q78: Can I filter specifically for Mentors?**
> Currently, the plugin treats Mentors like any other player. Specific mentor-based greetings are being considered for the "Sprout & Returner" style logic in a future update.

---

**Q79: How does WaveKeeper handle players with the "Roleplay" (RP) tag?**
> WaveKeeper doesn't have a specific RP tag filter yet, but you can use **Per-Player Emotes** to ensure your RP partners always get a specific, immersive greeting.

---

**Q80: Will it still emote at me if my status is set to "Busy"?**
> If someone else is using WaveKeeper and emotes at you, you will still see it. If *you* have your status set to "Busy", WaveKeeper will still fire your emotes unless you manually disable the plugin.

---

**Q81: What happens if I'm sitting on a chair or the ground?**
> WaveKeeper will fire the emote. Note that some emotes look different or may force your character to stand up depending on the specific animation.

---

**Q82: Can I use persistent/looping emotes like `/lean` or `/sweat`?**
> Yes. However, if you have **Emote Chain** or multiple greets firing, each new emote will cancel the previous looping animation.

---

**Q83: What if I have a macro named the same as my Emote Command?**
> WaveKeeper sends the command directly to the game's chat handler. It will prioritize the standard game emote over a player-created macro of the same name.

---

**Q84: I see a [WaveKeeper] error in red text. what does it mean?**
> This usually happens if an emote command was sent while you were in an invalid state (e.g., jumping or mid-animation). You can usually ignore these, or increase **Queue Spacing** to prevent overlaps.

---

**Q85: Do my settings carry over to my alt characters?**
> Settings are per-account by default in Dalamud. However, since WaveKeeper uses a **Profiles** system, you can create a specific profile for each alt and switch between them easily.

---

**Q86: How does WaveKeeper handle Hunt Trains or massive FATE crowds?**
> In extremely high-population areas, the game client limits the number of players it sends to your object table. WaveKeeper will only greet the players your game has actually loaded. In these cases, increasing **Scan Interval** is recommended to save CPU.

---

**Q87: Does the History log clear when I close the game?**
> No. The history is saved to your configuration file and will persist across sessions until you click **Clear History** in the Stats window.

---

**Q88: What specific columns are in the CSV export?**
> The CSV contains: `Time` (Timestamp), `Player` (Name + World), `Emote` (The command used), and `Type` (Greet, Reply, Mimic, or Goodbye).

---

**Q89: Can I use WaveKeeper on a Steam Deck or Linux?**
> Yes. As long as you are using XIVLauncher/Dalamud, WaveKeeper functions perfectly on Proton/Linux environments.

---

**Q90: Can WaveKeeper greet multiple people at the exact same time?**
> It scans everyone at once, but it uses the **Queue Spacing** to fire them one by one. This is intentional to prevent your character from trying to do five animations in a single frame.

---

**Q91: If two players enter my range at once, who gets greeted first?**
> WaveKeeper usually processes players in the order they appear in the game's object table, which is typically based on proximity or load order.

---

**Q92: Why did a player get greeted twice?**
> This can happen if the player left your **Greet Range** and returned after your **Re-Greet Cooldown** expired. Increase the cooldown if you find this happening too often.

---

**Q93: Can I use a sound file from my computer for the notification?**
> WaveKeeper currently only supports internal FFXIV sound IDs (1-100). Custom external audio is not supported to keep the plugin lightweight.

---

**Q94: Where can I report a bug or suggest a feature?**
> You can visit the official GitHub repository linked in the credits to open an Issue or join the community discussion.

---

**Q95: Is WaveKeeper open source?**
> Yes. The plugin is licensed under the MIT license, and the source code is available on GitHub for anyone to review or contribute to.

---

**Q96: Can I use facial expressions (e.g. /smile) as greetings?**
> Yes. Any standard slash command that triggers an emote or expression will work. Note that facial expressions often don't have a "motion" version, so the chat log will still show the text unless you use a plugin like "HideChat" or similar.

---

**Q97: Does WaveKeeper work in the Gold Saucer?**
> Yes. However, during active GATEs or in extremely crowded areas like the Aetheryte, player data might load slowly. Using a slightly higher **Scan Interval** (e.g., 5s) helps performance in these high-traffic hubs.

---

**Q98: What is the "Auto-Save" frequency?**
> WaveKeeper saves your configuration immediately every time you change a setting in the UI. Stats and history are saved periodically or upon a clean exit from the game.

---

**Q99: How much memory does the plugin use?**
> Memory usage is minimal, typically under 10MB. The largest memory consumption comes from the **Greet History** log, which is capped at 500 entries to ensure stability.

---

**Q100: Can I sync my settings across multiple PCs?**
> Yes. You can use a cloud-sync service like OneDrive or Dropbox to symlink your `pluginConfigs` folder, or manually copy the `WaveKeeper.json` file between machines.

---

**Q101: Does WaveKeeper detect "Away" status if someone uses the /away command?**
> Yes. WaveKeeper looks for the official "Away" icon (the red chair). If a player has manually set themselves to Away, they will be caught by the **Ignore AFK Players** filter.

---

**Q102: Can I use WaveKeeper in my Island Sanctuary?**
> Yes. Island Sanctuaries are considered regular zones. Since only invited friends or party members can visit your island, the "Friends Only" mode works perfectly there.

---

**Q103: Does it work while I'm using the "Perform" (Bard music) actions?**
> No. FFXIV blocks standard emotes and most commands while you are in Performance mode to prevent audio-visual desync. WaveKeeper will queue the emotes, but they will likely fail until you stop performing.

---

**Q104: How do I resize the Compact window?**
> The Compact window is designed to be as small as possible and auto-resizes based on its content. You can move it anywhere on your screen, but it does not have a manual "drag-to-resize" handle.

---

**Q105: What happens if I have "Simple Tweaks" auto-targeting enabled?**
> There should be no conflict. WaveKeeper performs its own targeting calls which are standard game functions. If both plugins try to target different things at once, you might see a brief "targeting flicker."

---

**Q106: Does it work with the "New World" or "Road to 90" bonus status?**
> Yes. WaveKeeper sees all standard player metadata. While there isn't a specific filter for "New World" players yet, they are treated as standard players for all greeting logic.

---

**Q107: Can I use /em (Custom Emote) commands?**
> Yes. You can type things like `/em waves happily at <t>` into the emote command box. WaveKeeper will send this exactly as written, allowing for personalized, narrative-style greetings.

---

**Q108: Will WaveKeeper fire if I'm in the middle of a trade?**
> No. FFXIV usually blocks emote animations while the trade window is open. The plugin may try to send the command, but the animation will likely be suppressed by the game client.

---

**Q109: Does the "Re-Greet Cooldown" persist after I zone?**
> No. When you change zones, the "already greeted" list is wiped clean. This ensures you greet your friends again when you meet them in a new location.

---

**Q110: Can I use WaveKeeper in the Firmament?**
> Yes. The Firmament is a high-traffic social hub where WaveKeeper is very popular. Be sure to set a natural **Greet Delay** (3-5s) to avoid greeting every single person running past the Aetheryte.

---

**Q111: Does WaveKeeper use much CPU?**
> No. The scanning logic is highly optimized and only runs once every few seconds (based on your Scan Interval). It has a negligible impact on your CPU and FPS.

---

**Q112: Can I customize the "Targeting" behavior?**
> Currently, the plugin uses a standard "Hard Target" call. We are exploring "Soft Target" or "Focus Target" options for future updates to be less intrusive.

---

**Q113: Is there a way to see how many people I've greeted ever?**
> Yes. Check the **Stats** window for the "Total Greets" counter. This value is saved permanently in your config file.

---

**Q114: Does WaveKeeper support "Chat Filter" settings from the game?**
> Yes. If you have emotes disabled in your standard FFXIV chat settings, the text won't appear for you, but the plugin will still fire the animations.

---

**Q115: What is the "Queue Size" in the Compact window?**
> This shows how many emotes are currently waiting to fire. If you see this number getting very large, it means you're in a crowded area and may need to increase your **Queue Spacing**.

---

### 🍹 Club & Venue Hosting (Upcoming Features)

*The following features are planned for future releases to better support club greeters and venue hosts.*

---

**Q116: Does WaveKeeper work in Frontlines or Crystalline Conflict?**
> Technically yes, if you disable the "Duty Filter." However, it is highly discouraged as it can be distracting during competitive play and might target teammates instead of enemies.

---

**Q117: Can I use it in Deep Dungeons like Palace of the Dead?**
> Yes. If the Duty Filter is off, it will work. It can be a fun way to greet your party members as you progress through floors.

---

**Q118: Does it detect the "First Time" bonus in a duty?**
> Not specifically. It primarily looks for "Sprout" or "Returner" status icons. We are looking into "First Timer" detection for a future update.

---

**Q119: What if two players have the same name but are from different worlds?**
> WaveKeeper stores player names with their home world data in the "already greeted" list, so it correctly distinguishes between "John Doe [Gilgamesh]" and "John Doe [Leviathan]."

---

**Q120: Does it trigger when I look at someone's Adventurer Plate?**
> No. WaveKeeper triggers based on proximity and emote events. Opening a plate or a portrait window does not trigger a greeting.

---

**Q121: Can I use it while queuing for a Duty Roulette?**
> Yes. The plugin remains active while you are in the queue. It only pauses once the duty actually begins (if the Duty Filter is enabled).

---

**Q122: Does it work in the Inn Room while using "The Unending Journey"?**
> Since you are usually alone in the Inn room, there is no one to greet. Additionally, cutscenes triggered by the book will pause the plugin if your "Cutscene Filter" is on.

---

**Q123: What happens if I enter "Gpose" (Group Pose)?**
> Most commands are blocked by the game client while in Gpose. WaveKeeper will stop firing emotes until you exit the Gpose interface.

---

**Q124: What is the absolute minimum "Queue Spacing"?**
> The slider goes down to 0.5s, but typing `0` manually in the config is the absolute minimum. Note that `0` may cause the game to "swallow" emotes if too many fire in a single frame.

---

**Q125: Why is the WaveKeeper icon red in my /xlplugins menu?**
> This usually means the plugin failed to load. Check `/xllog` for error messages. It often happens after a major FFXIV patch if the plugin hasn't been updated for the new API level.

---

**Q126: I get a "Command not found" error when typing /wavekeeper.**
> This means the plugin isn't loaded. Ensure it is installed and "Enabled" in the `/xlplugins` menu.

---

**Q127: Does it conflict with the "TextAdvance" plugin?**
> No. TextAdvance handles dialogue skipping, while WaveKeeper handles emotes. They operate on different systems and can be used together safely.

---

**Q128: Is WaveKeeper compatible with "YesAlready"?**
> Yes. WaveKeeper doesn't interact with confirmation dialogs, so YesAlready won't interfere with its operation.

---

**Q129: Can it detect if a player is wearing an Eternal Bond ring?**
> Currently, WaveKeeper does not scan player equipment. It only looks at the player's name, world, and status icons (Sprout, etc.).

---

**Q130: Can I set a specific emote for Lalafells (like /pet)?**
> While there isn't a "Per-Race" filter yet, you can use the **Per-Player Emotes** list to set `/pet` for your specific Lalafell friends.

---

**Q131: Does it greet players on mounts, or the mounts themselves?**
> It greets the player character riding the mount. It ignores the mount entity.

---

**Q132: Can it detect FC Ranks (e.g., greeting only the Leader)?**
> No. The FFXIV API doesn't provide rank data for players who aren't in your own Free Company in a way that is easily scannable in the open world.

---

**Q133: Does WaveKeeper help with Gold Saucer GATE participation?**
> It can help you find and greet people during GATEs like "Leap of Faith," making the wait for the next jump more social.

---

**Q134: Can I use it while gathering in the Diadem?**
> Yes. It will greet other gatherers as you fly between nodes. Be sure to enable the **Gathering Filter** if you find it distracting while trying to hit nodes.

---

**Q135: Does it interact with Minions?**
> No. WaveKeeper ignores minions. Standard game emotes like `/beckon` or `/handover` only affect minions if you have them targeted manually.

---

**Q136: My DTR icon (WK) disappeared. How do I get it back?**
> Ensure **DTR Bar Toggle** is enabled in the General settings. If it's still missing, try toggling it off and on again.

---

**Q137: I'm seeing the [WaveKeeper] chat prefix twice. Why?**
> This happens if you have two different plugins trying to echo the same message, or if you've manually added the prefix to your custom chat settings. Check your **Chat Prefix** setting.

---

**Q138: Is it safe to leave WaveKeeper running 24/7?**
> Yes. It is highly optimized and uses very few resources. It will safely idle whenever no one is around or while you are AFK.

---

**Q139: Is AI-integrated chat (like GPT) planned?**
> There are no current plans to integrate AI chat models into WaveKeeper. The focus remains on automated emotes and social "fluff" rather than complex conversation.

---

**Q140: What is the difference between "Zone Warmup" and "Scan Interval"?**
> **Zone Warmup** is a one-time delay when you first enter a map. **Scan Interval** is the recurring timer that checks for new players while you stay in that map.

---

**Q141: Will it fire if I'm turned into a Frog or Toad?**
> The game blocks most emotes while you are transformed. WaveKeeper will try to send the command, but your character won't perform the animation.

---

**Q142: Does it detect "Newbie" world status (for the double XP)?**
> No. It only detects the player's local status (Sprout/Returner). The "New World" status is a server-wide buff and not a per-player icon WaveKeeper can scan.

---

**Q143: Why is it greeting people behind me?**
> WaveKeeper scans in a 360-degree radius around your character. It doesn't matter which way you are facing; if they are in range, they are detected.

---

**Q144: Can I share my profiles with other players?**
> Yes. You can copy the profile block from your `WaveKeeper.json` file and send it to a friend. They can paste it into their own config file to mirror your settings.

---

**Q145: Does the "Daily Greet Counter" count the same person twice?**
> No. It only increments when a player is successfully added to the "already greeted" list for that day.

---

### 🍹 Club & Venue Hosting (Upcoming Features)

*The following features are planned for future releases to better support club greeters and venue hosts.*

---

**Q146: Does WaveKeeper work at the Mahjong tables in the Gold Saucer?**
> No. When you are seated at a Mahjong table, you are entered into a special mini-game state where most emotes and external character actions are disabled.

---

**Q147: Can I use it to greet people during "Blue Mage" log runs?**
> Yes. If you have your party filter on, it’s a great way to stay social during the downtime between pulls in Blue Mage content.

---

**Q148: Does it detect "Shared FATE" progress icons?**
> No. WaveKeeper currently only focuses on social status icons (Sprout, Mentor, AFK) and friend/FC membership.

---

**Q149: Does the Scan Range account for height (the Y-axis)?**
> Yes. The distance calculation is 3D. If someone is standing 15 yalms directly above you on a bridge, they will be detected just like someone 15 yalms away on the ground.

---

**Q150: What if I'm crafting but not moving? Does AFK filter trigger?**
> If you are actively using a crafting macro or clicking "Synthesize," the game considers you active. If you finish crafting and stand there for 2 minutes without moving, the AFK filter will likely trigger.

---

**Q151: Does it work at the Wolves' Den Pier?**
> Yes. Since the Wolves' Den Pier is a social hub and not an active match, WaveKeeper works normally there.

---

**Q152: Can it detect if I'm a "Guest" at a wedding (Eternal Bond ceremony)?**
> No. WaveKeeper doesn't have access to your inventory or specific invitation status. It only sees the players physically present in the room with you.

---

**Q153: Does it greet people while I'm doing the "Fashion Report"?**
> While you are in the menu being judged by Masked Rose, your character is in a "busy" state, and emotes may not fire correctly.

---

**Q154: Can I use it in "Lord of Verminion" or "Chocobo Racing"?**
> No. These mini-games enter a separate instance/state where standard character emotes and commands are blocked by the game.

---

**Q155: Can it see "Ranked" PVP status icons (like Crystal rank)?**
> Currently, no. WaveKeeper is focused on standard social icons. Expanded icon detection for PVP ranks is a possible future feature.

---

**Q156: Does it fire while I'm editing a glamour at the Glamour Dresser?**
> No. Using a Glamour Dresser or the Armoire locks your character into a menu state that prevents animations from playing.

---

**Q157: Will it greet my Retainer when I summon them?**
> No. Retainers are considered special entities/NPCs by the game when summoned to a bell, and WaveKeeper is configured to only interact with player characters.

---

**Q158: Does it work on "Ocean Fishing" boats?**
> Yes! It’s a very popular way to greet fellow fishers. However, keep in mind that animations are often interrupted by the fishing action itself.

---

**Q159: Can I use it in the Bozjan Southern Front or Zadnor?**
> Yes. These "exploratory missions" are treated like zones. WaveKeeper will greet nearby players as you ride between skirmishes or critical engagements.

---

**Q160: Does it interact with "Lost Actions" in Bozja?**
> No. WaveKeeper only handles standard emotes and does not have the ability to trigger Lost Actions or specific Bozjan mechanics.

---

**Q161: How does it handle "Notorious Monsters" (NM) in Eureka?**
> WaveKeeper is great for greeting the massive crowds at Eureka NMs. Just remember to use a high **Scan Interval** (5s+) to keep your CPU usage low in those 100+ player crowds.

---

**Q162: Can WaveKeeper cause FFXIV to crash?**
> It is very rare. WaveKeeper is built to be "thread-safe" and uses standard Dalamud hooks. If a crash occurs, it’s usually due to a conflict with another plugin that also hooks into the emote system.

---

**Q163: Why are emotes firing but my character isn't moving?**
> This can happen if you have another plugin (like "NoAnimation") disabling your character's movements, or if you are in a state where the game suppresses animations (like being mounted or jumping).

---

**Q164: How can I help translate the plugin into my language?**
> You can submit a pull request on the GitHub repository with updated localization files. We appreciate community contributions!

---

**Q165: Is WaveKeeper written in C#?**
> Yes. Like almost all Dalamud plugins, it is written in C# and utilizes the .NET framework provided by the game's launcher environment.

---

**Q166: Does it use the "Lumina" library?**
> Yes. It uses Lumina to read the game's internal data sheets (like the Emote sheet) to understand which commands are available to your character.

---

**Q167: Does WaveKeeper use any external APIs or call home?**
> No. WaveKeeper is entirely self-contained. It does not send any of your data to external servers and does not require an internet connection to function (other than for updates via Dalamud).

---

**Q168: Is WaveKeeper considered "botting"?**
> This is a gray area. Technically, any automated action could be viewed as "botting" under a strict interpretation of the ToS. However, since it only performs social emotes and doesn't grant a gameplay advantage, it is generally considered a "social fluff" plugin.

---

**Q169: Can I get banned for using WaveKeeper?**
> As with all third-party tools, there is a non-zero risk. However, there have been no recorded bans for using WaveKeeper. To stay safe, don't use it to spam people in a way that would cause them to report you for harassment.

---

**Q170: Can it fire my mount's special "Mount Action" emote?**
> No. WaveKeeper only supports standard character emotes. It cannot trigger specific actions tied to a mount's action bar.

---

**Q171: What if I use a "Pyroglyph" or other transformation item?**
> Transformations usually lock your character out of standard emotes. WaveKeeper will send the command, but nothing will happen until the transformation wears off.

---

**Q172: Does it work in the "Hall of the Novice"?**
> Since the Hall of the Novice is a solo instance, there are no other players to greet.

---

**Q173: Can I use it while interacting with "Custom Deliveries" NPCs?**
> You can, but while the NPC dialogue or delivery menu is open, your character is locked and cannot perform emotes.

---

**Q174: Does it work in the Doman Enclave?**
> Yes. The Doman Enclave is a standard social zone where other players can be found and greeted.

---

**Q175: Does it detect "Trial" accounts?**
> It treats Trial accounts the same as full accounts. As long as they have a Sprout or standard icon, WaveKeeper will interact with them.

---

**Q176: Does it respect the game's internal "Blacklist" or "Mute" list?**
> No. WaveKeeper reads data from the object table. If you want to ignore someone you have blacklisted in-game, you must also add them to the **WaveKeeper Ignore List**.

---

**Q177: Can it distinguish between a "Free Company Tag" and the "FC Name"?**
> WaveKeeper looks at the internal FC ID of a player. It uses this to determine if they are in your Free Company, regardless of what their tag says.

---

**Q178: How does it handle the "Wanderer" tag?**
> It recognizes Wanderers as players from other worlds on your same Data Center. They are greeted normally unless your filters say otherwise.

---

**Q179: How does it handle the "Traveler" tag?**
> Similar to Wanderers, Travelers (from other Data Centers) are treated as standard players.

---

**Q180: Does it work in the "Baldesion Arsenal"?**
> Yes, if the Duty Filter is off. It’s a great way to stay social during the long wait times inside BA.

---

**Q181: Does it work in "Delubrum Reginae"?**
> Yes, again provided the Duty Filter is off.

---

**Q182: In an Alliance Raid, does it greet people in the other two parties?**
> Yes. WaveKeeper sees all players in the instance. If you have "Everyone" mode on, it will wave at members of Party B and C just like your own.

---

**Q183: Does it work in "Rival Wings"?**
> Only if the Duty Filter is off. Like Frontlines, we recommend caution here as it can be distracting.

---

**Q184: What if I'm a visitor in someone else's Island Sanctuary?**
> It works perfectly! You can greet the owner and any other guests they have invited.

---

**Q185: Does WaveKeeper use hardcoded emote lists?**
> No. It reads the `Emote` sheet from the game files, so it automatically supports any new emotes Square Enix adds in future patches.

---

**Q186: Can I see debug details in the Dalamud Console?**
> Yes. If you enable **Debug Logging**, you can see detailed information about every scan and emote event in the `/xllog` window.

---

**Q187: My profiles aren't saving. Why?**
> Ensure that FFXIV has permission to write to your `AppData` folder. Sometimes antivirus software blocks Dalamud from saving configuration files.

---

**Q188: Is there a Discord for WaveKeeper?**
> Yes! Check the **Support** section of the README for a link to our community Discord server.

---

**Q189: Why is my "Daily Greet Date" weird in the config?**
> It uses a standard `YYYY-MM-DD` format. If it looks strange, it might be due to a local system clock sync issue.

---

**Q190: Can I use WaveKeeper to find "hidden" Lalafells in a pile?**
> It doesn't "find" them visually, but it will certainly wave at them if they are in your range, which might help you locate them!

---

**Q191: Does it greet players who are currently "Dead"?**
> No. WaveKeeper filters out players with 0 HP or the "Dead" status to avoid sending awkward emotes to people waiting for a raise.

---

**Q192: Can I use it in the "Battlehall" (Triple Triad)?**
> Yes, but like Mahjong, if you are actively in a match, your emotes will be blocked by the game.

---

**Q193: Does it fire while I'm using a "Venture" menu for my retainer?**
> No. While any retainer menu is open, your character's actions are locked.

---

**Q194: What happens if I use WaveKeeper during a "Wedding" ceremony?**
> We strongly recommend disabling it during the actual ceremony to avoid your character waving at the couple during serious cutscenes or vows!

---

**Q195: Does WaveKeeper have a "Silent Mode"?**
> Yes. You can disable all chat notifications and sound alerts in the **Chat & Sound** settings to make the plugin completely silent.

---

### 🍹 Club & Venue Hosting (Upcoming Features)

*The following features are planned for future releases to better support club greeters and venue hosts.*

---

**Q196: Can WaveKeeper send a custom text message (Tell/Say/Yell) when someone arrives?**
> ⏳ **Planned:** A "Custom Greeting Message" feature is in development, allowing you to send a text greeting (like "Welcome to the club!") alongside your emote.

---

**Q197: Can I include the player's name in my custom greeting message?**
> ⏳ **Planned:** We are working on placeholder support (e.g. `{name}`) so you can personalize your automated greetings.

---

**Q198: Can I set up a "Zone Anchor" to only greet people at the door?**
> ⏳ **Planned:** This will allow you to set a coordinate point (the venue entrance) so you only greet people walking in, rather than everyone inside the building.

---

**Q199: Can I send guest logs to a Discord Webhook?**
> ⏳ **Planned:** Venue owners will eventually be able to link a Discord webhook to get real-time (or batched) notifications of who visited their venue.

---

**Q200: Can I ignore fellow staff members or specific FC ranks?**
> ⏳ **Planned:** We are investigating a way to filter out players based on their FC rank or specific "Staff" titles to avoid greeting your own team.

---

## 🛠️ Support

If you encounter any issues or have suggestions, feel free to open an issue on GitHub.

- [**Discord **](sm0var)

---

## 🙏 Credits

**Made by sm0var**

Thanks to Kingo, Iridescent, Sora, Brit, Willow & Wyno 💜

---

## 📜 License

This project is licensed under the [MIT License](https://github.com/sm0kez/WaveKeeper/blob/main/LICENSE).
