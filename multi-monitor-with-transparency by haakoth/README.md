* Developer: haakoth <rkeever at pm.me>
* Multi monitor with transparency:

  1. It has single and multi monitor config, transparency, allows for env for tray and cpu temp, and other custom modules
  
Using multi monitor/single config

The launcher.sh will handle a single monitor, or three monitors. This was designed for a laptop with 2 external monitors, and matches primary, HDMI-0 and eDP-1-1. You will need to edit for your hardware/use.

A launch.sh.simple is included for single monitor only.


Using Transparency

To save someone time, if they might not know, i3 sets transparency at the end of color hex codes, while polybar sets it at the beginning. 
i3      - #b48eadcc
polybar -  #ccb48ead

There are three transparent colors, bg/tbg, grey/tgrey, and orange/torange. Replace tbg with bg, to remove transparency.


Env settings for tray and cpu

My hardware occasionally uses hwmon7, then after a cold boot will use hwmon8 the next time for the cpu path (and vice versa). The launcher.sh checks for the path and sets an env variable to be used by the module. If you use the simple launch, this logic will need to be uncommented. The original hardcoded module is included and may be used if this is not the case in your situation.

The tray env is set/passed from launcher.sh in one of the two lines for primary display


Custom/modified modules (acknowledgement when known are in modules.ini of top of script)

The following 3, both modules have the same name, and one must at a minimum must be commented
temp-cpu 
  - internal standard harcoded path (commented)
  - modified to use env HWMON_PATH provided by launch.sh, launch.sh will need to be edited for appropriate hwmon
temp-gpu 
  - internal (commented)
  - modified for nvidia-smi
powermenu 
  - EOS i3 (commented)
  - Expand left, reboot and shutdown only options (unknown author)

wireguard 
  - Simple connect/disconnect icon using nmcli cmd, and the grep can easily be modified for other vpn type connections

cns caps/num 
  - script from EOS bswpm for Cap and Numlock indicator

arch-updates
uptime
Launchers term, thunar, firfox, edge, steam

Many thanks to bitterhalt for his tokyo-night polybar implementation, which this was derived from.