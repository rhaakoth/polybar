* Developer: haakoth <rkeever at pm.me>
* Multi monitor with transparency:

  1. It has single and multi monitor config, transparency, allows for env for tray and cpu temp, and other custom modules
  
Using multi monitor/single config

The launcher.sh will handle a single monitor, or three monitors. This was designed for a specific solution to a laptop with 2 external monitors, and matches primary, HDMI-0 and eDP-1-1. You will need to edit for your hardware/use.

A launch.sh.simple is included for single monitor only.


Using Transparency

This took me a minute, so thought I would mention for those that are not aware. i3 uses transparency at the end of color hex codes, while polybar uses it at the beginning.
i3      - #b48eadcc
polybar -  #ccb48ead

The original color is defined, so just replace tbg with bg for example on the background, to remove transparency. (tgrey and torange are also used)


Env settings for tray and cpu

My hardware occasionally uses hwmon7, and after a cold boot will use hwmon8 the next time for the cpu path. The launcher.sh checks for the path and sets an env variable to be used by the module. The original hardcoded module is included and may be used if this is not the case in your situation.

The tray env is set/passed from launcher.sh in on one of the two lines for primary display


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