This is a simple bash script that allows you to replay mouse clicks and key presses thus allowing you to execute Aegisub plugins with a single keypress.

https://user-images.githubusercontent.com/65547311/202894369-e6e8eae6-fd21-48df-b056-b48111c7761e.mp4

## Requirements
* xdotool - To emulate keypresses and mouse clicks
* rofi - launcher to select which Aegisub script to execute
* yad - if you need file selector
* notify-send - to show messages as notification (since we won't be running the script in terminal)
* Basic shell scripting knowledge

## What you can do with this script

* Run any scirpt from Automation menu in one click (No matter how many key presses or mouse clicks it needs)
* Chain execution of scripts just like [arch1t3cht's Aegisub Chain](https://github.com/arch1t3cht/Aegisub-Scripts#aegisubchain)
* Allow file selection for scripts like Aegisub Motion, svg2ass etc.
* Do anything you can in bash scripts really
* No need to remember hotkeys since you can now fuzzy search them using the script's name, author's name or feature's name.

## Limitation

* I use a tiling windows manager so the windows's dimension and position do not change. If they change in your distro, you cannot use this script.
* If you constantly add new plugins, the co-ordinate of the plugin in Automation menu will also change. To prevent that, I add all of my most used scripts in sub-menu as shown in the image below so their position will always remain same even if I add new plugins. You can add script to sub-menu using Dependency Control's `Macro Configuration` or modifying depctrl's json file itself.

![auto](https://user-images.githubusercontent.com/65547311/202894970-6b73e70f-ce79-4ee6-8e84-aaf42faa177f.png)

* You use Windows.
* You use Linux but Wayland. I hear `ydtool` is `xdotool` equivalent for Wayland so you'll have to adapt with that.

## Template

Your screen size is different than mine so the script I write for my computer will not work in yours. So I've provided a [template](https://github.com/PhosCity/Aegisub-xdotool/blob/main/template) where you can add your own xdotool commands. You are however free to check [my script](https://github.com/PhosCity/Aegisub-xdotool/blob/main/aegisub) to see what can be done with this script.

## Recording xdotool commands

If you want to do it manually, you can get the location of your mouse cursor by using `xdotool getmouselocation`. However I've written a [bash script](https://github.com/PhosCity/Aegisub-xdotool/blob/main/record-coordinate) to somewhat automate the process.

When you run this script, if your mouse cursor remains unmoved for a couple of seconds, a prompt will appear.

![record](https://user-images.githubusercontent.com/65547311/202895143-a7d09920-3ada-4544-8938-b679e22553b7.png)

If the prompt showed accidentally or when you weren't ready, you can select `Continue wihout recording`. If at any point you want to stop recording, select `Stop Recording` instead.

However if you want to record current location, type a message. For example, if you type `Automation Menu` and hit Enter, your location will be recorded with comment `Click on Automation Menu`. 

If you want to record key press instead of mouse clicks, type `t msg` where `t` tells the script that you want to record keyboard typing and `msg` is what you want to type. For example, `t ctrl+v` will emulate you pressing `ctrl+v` in your keyboard.

https://user-images.githubusercontent.com/65547311/202895201-b655614b-3da1-401f-a662-56f3faf0a452.mp4

## Inspiration

[Zahuczky's Second Typesetting Keyboard](https://github.com/Zahuczky/2nd-typesetting-keyboard)
