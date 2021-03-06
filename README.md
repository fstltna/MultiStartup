# Multicraft Startup Scripts (1.1)
Startup scripts for the Multicraft sandbox software - uses the "screen" command to manage sessions. This also restarts the Multicraft process if it crashes.

Official support sites: [Official Github Repo](https://github.com/fstltna/MultiStartup) - [Official Forum](https://minecity.online/index.php/forum/startup-scripts)  - [Official Download Area](https://minecity.online/index.php/downloads/category/5-server-tools)
![Minetest Sample Screen](https://MineCity.online/minetest_demo.png) 

---
These start up the Multicraft server at boot time with a "screen" process.

1. Copy **multicraft** into **/home/mtowner/bin** - make sure it is executable
2. Copy **startmulticraft** into **/home/mtowner/MultiCraft2** - make sure it is executable
3. Put **@reboot /home/mtowner/bin/multicraft start** into your crontab
4. Put **@reboot /home/mtowner/bin/startrelay** into your crontab
5. Run the relay setup:
	pip install aiohttp
	pip install discord.py
	cd /home/mtowner
        unzip MultiStartup/MyRelay.zip
        cd /home/mtowner/MultiCraft2/mods/discordmt
        vi relay.conf # Set the discord bot info where needed
	Activate the bot with: https://discordapp.com/oauth2/authorize?client_id=CLIENTID&scope=bot
        Run startrelay
        Restart the multicraft server, and enable the discordmt

When you want to view the Multicraft console, just enter "**screen -r**" in your shell.

To disconnect from the Multicraft console just press **CTRL-A CTRL-D**. This will leave it running and you can reconnect to it again.

If you want to turn off the server respawning type "**touch /home/mtowner/MultiCraft2/nostart**". To reenable it type "**rm /home/mtowner/MultiCraft2/nostart**".

---
Note: If you don't already have the "screen" tool installed you will need to install it by "**sudo apt-get install screen**".
