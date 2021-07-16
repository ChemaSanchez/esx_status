# Script Original From ESX-Org
FXServer esx_status  | Chema Leaks
[INSTALLATION]

1) CD in your resources/[esx] folder

```
3) Import esx_status.sql in your database
4) Add this in your server.cfg :

```
start esx_status
```

[HOWTO]

server.lua
```lua

local name    = 'hunger'
local default = 1000000
local color   = '#CFAD0F'

TriggerEvent('esx_status:registerStatus', name, default, color, 
	function(status) -- Visible calllback, if it return true the status will be visible
		return true
	end,
	function(status) -- Tick callback, what to do at each tick
		status.remove(200)
	end,
	{remove = 200} -- Client action (add / remove) so the client can be in sync with server
)


```
