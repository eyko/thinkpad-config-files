# Thinkpad X230 configuration files and scripts

This repository contains some useful and reusable configuration files for
the Thinkpad X230 (on Linux, mostly).

### Generic config files
Almost everything else is as generic as I was able to make it. I've taken some
inspiration from Crunchbang (awesome distro btw) to add some Keybindings to
Openbox. Crunchbang also used some handy scripts (e.g. the PythonGTK logout
dialog) to make using the desktop less of a hurdle for beginners. I've taken a 
lot from Cruchbang. To be honest, I started this as a way of implementing most
of Crunchbang in Arch Linux. I know Archbang exists, but I'm more comfortable
running just Arch, since Archbang could be considered a different distro
altogether.

I haven't had any issues so far and life has been much easier on the Arch side,
so I really recommend any Archbang or Crunchbase users to give Arch a go!
Installation can be slow but it's easy and straightforward. And this repo should
also be of some help.

### Thinkpad X230 specific files
Most config files can be reused and are not Thinkpad specific. Thinkpad specific
files are mainly:

* Kernel config: only necessary drivers are selected to be built into the
  kernel [\*] or loaded as modules [m]. All other drivers are ignored. This
  allows for quicker kernel compilation as most modules will be skipped. Other
  kernel settings that are enabled/disabled are purely based on personal choice.
  I'm usually using the `linux-ck` kernel (Linux Kernel with Con Kolivas'
  patchset) but the config file might work on others. Notable differences are
  the inclusion of the Brain Fuck Scheduler. You can read some more in the
  [Arch Linux linux-ck](https://wiki.archlinux.org/index.php/linux-ck#Further_Reading_on_BFS_and_CK_Patchset)
  page.

* Driver tweaks: I've chosen to compile some drivers as kernel modules so that
  I can load them during boot with some boot flags. Most notably, the X230's
  wifi driver has some issues with N speeds and with power saving... so I've 
  disabled wifi_n and enabled some other flags. More info in the
  [X230](https://wiki.archlinux.org/index.php/Lenovo_ThinkPad_X230) page on the
  Arch Linux wiki.

* X11/xorg: The TrackPoint (red nipple) is usually a Thinkpad only thing. Some
  other laptops come with it but make sure you update the `Match` string if you
  plan on using these config files as there can be many configurations and/or
  vendor strings. I mostly only configure the trackpoint to use middle button 
  scrolling. I want to add some patches here to syndaemon that allows the user
  to disable the Trackpad when the TrackPoint is in use. This hasn't made it
  upstream yet and isn't stable enough for production so I might hold back for
  a bit on that. 

* Media Keys: I mostly use Openbox, and have bound the Thinkpad's VolumeUp and
  VolumeDown, Mute, and MicMute keys to use amixer (personal preference of mine
  over pulseaudio) to toggle / increase / decrease their respective channels.
  It works well for me but I can see how things could go south if used together
  with pulseaudio. Have that in mind.


