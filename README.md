awesomeTempWidget
=================

Idea
--------

The idea was to create a simple widget that shows current CPU-temperatur
in awesome wm. The temperature is gathered by ACPI and processed using the
Lua-script language.

Original idea by [schtibe](https://github.com/schtibe "")

Requirements
--------

ACPI subsystem

Usage
--------

Place the temperatur.lua file somewehere your awesome-wm can read it. Then put the following in your rc.lua

> temp = require("temperatur")
> myTempWidget = widget({type = "textbox", align = "right"})
> awful.hooks.timer.register(1, function() myTempWidget.text = temp.getTemp(60, 70) end)

if you want the update intervall to be higher, say 10 seconds, you need to adjust the hook as follows

> awful.hooks.timer.register(**10**, function() myCpuWidget.text = temp.getCpuTemp(60, 70) end)

Now you need to add your widget to the wiibox:

> mywibox[s].widgets = { ...
>                        myTemperaturWidget,
>                        ...
>                      }

Restart your awesome wm and you should see the temperatur widget.

License
--------
GPL
