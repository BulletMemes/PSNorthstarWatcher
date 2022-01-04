# Features
- Can watch multiple servers.
- Detect if server is running by port actually being used (Auth. port) and restart.
- Restart your servers after a certain amount of time.
- Log cleanup. Don't let the logs fill up your disk space.
- Gather crash logs in a central folder.
- Can generate an index.html with Server browser info (enabled be default, open index.html).
- See uptime of your Titanfall servers.

# PSNorthstarWatcher description
faky's really bad Powershell Northstar Server Watcher. Use at own risk. It is very minimalistic.

# L1ghthouse's PS Script
https://github.com/l1ghthouse/NorthstarScripts
Its really good, go have a look!

# How-To
For this example we are going to assume your Titanfall2 Game is at `C:\Program Files (x86)\Origin\Titanfall2`
Then you create new subfolders (eg Origin\Titanfall2-1, Titanfall2-2) for each server. I recommend using symbolic links instead of copying the entire Titanfall2 folder.
1) Copy zip files to -> C:\Program Files (x86)\Origin
2) Rename `example-northstar server watcher-config.ps1` to `northstar server watcher-config.ps1` 
3) Open `northstar server watcher-config.ps1` with a text editor (notepad).
4) Edit following variables:
5) `$originpath = "C:\Program Files (x86)\Origin\"`
6) `$gamedirs = @("Titanfall2-1","Titanfall2-2")` add folder name for each Titanfall2 instance
7) `$tcpportarray = @(8081,8082)` add TCP port for each Titanfall2 instance
8) `$udpportarray = @(37015,37016)` add UDP port for each Titanfall2 instance
9) Save file. 
10) Changing other variables is optional, but possible
11) Change `ns_startup_args_dedi.txt` and `autoexec_ns_server.cfg` if needed (these are Northstar config files).

So folder structure should look like this:
- C:\Program Files (x86)\Origin
  - `run Northstar Server Watcher.bat`
  - `northstar server watcher-config.ps1`
  - `northstar server watcher.ps1`
  - `engineerrorclose.exe`
  - `Titanfall2`
  - `Titanfall2-1\R2Northstar`
  - `Titanfall2-2\R2Northstar`

Now start `run Northstar Server Watcher.bat`. 

# AHK/EXE Files
These are used for some weird workaround when the server spits message boxes. (engineerrorclose.exe)
