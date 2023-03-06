* Developer: haakoth <rkeever at pm.me>
* Multi monitor with transparency:

  1. It has single and multi monitor config, transparency, allows for env for tray and cpu temp, and other custom modules
  
Using multi monitor/single config

The launcher.sh will handle a single monitor, or three monitors. This was designed for a specific solution to a laptop with 2 external monitors, and matches primary, HDMI-0 and eDP-1-1. You will need to edit for your hardware/use.

A launch.sh.simple is included for single monitor only.


Using Transparency

To save someone time, if they might not know, i3 sets transparency at the end of color hex codes, while polybar sets it at the beginning. 
i3      - #b48eadcc
polybar -  #ccb48ead

There are three transparent colors, bg/tbg, grey/tgrey, and orange/torange. Replace tbg with bg, to remove transparency.


Env settings for tray and cpu

My hardware occasionally uses hwmon7, then after a cold boot will use hwmon8 the next time for the cpu path (and vice versa). The launcher.sh checks for the path and sets an env variable to be used by the module. If you use the simple launch, this logic will need to be uncommented. The original hardcoded module is included and may be used if this is not the case in your situation.

The tray env is set/passed from launcher.sh in one of the two lines for primary display


Custom/modified modules

arch-updates
temp-cpu -modified to use env HWMON_PATH in launch.sh
temp-gpu -(2) internal (commented), modified for nvidia
uptime
wireguard 
powermenu -(2) EOS i3 (commented), modified from unknown author
cns caps/num - script from EOS bswpm
Launchers term,thunar, firfox, edge, steam

Additional reference in scripts

Many thanks to bitterhalt for his tokyo-night polybar implementation, which this was derived from.