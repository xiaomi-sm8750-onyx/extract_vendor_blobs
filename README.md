``Vendor Blob Extraction (v2)``

9/21/2021 · 2 min read

This is the updated instructions, and an update-to-date (as of writing) how-to guide for vendor blob extraction

Unlike the earlier guide, you won't need the full rom synced. Huge kudos to the guys at LineageOS for making this possible!

What you would need:

Around like 20GB of disk space (just to be safe)
Dump or OEM zip whichever is available
A Popular GNU/Linux Distro
Where to search if your zip is dumped already?

Go to this link: https://dumps.tadiphone.dev/dumps

Use the search box to search your device name
If you find your device repo there, go in, and see its vendor or system build.prop if any prop matches what you need.
It's more of visual exploration for you now.

If the build you have is newer/the device is missing, you can request for it to be dumped here:
https://t.me/dumprequests

In the meanwhile, you can also dump it yourself, rather than waiting for it to be dumped.

Download the concerned OEM zip (like MIUI, OneUI, or whatever)

Dumpyara is a universal dumper script compatible with almost all OEM zips

``git clone https://github.com/AndroidDumps/dumpyara``

``cd dumpyara``

If you have Arch Linux or Ubuntu, then simply run,

``bash setup.sh``

else, you have to poke into that script and match accordingly with the deps for your distro.

With the setup part done,
Let's get to the dumping part.

``bash dumpyara.sh ./zipname.zip``

Let it run for a while, and your dump should be at the working/zipname folder of dumpyara

Once you have the dump, let's start to extract from it.

``git clone https://github.com/LineageOS/android_tools_extract-utils android/tools/extract-utils``


``git clone https://github.com/LineageOS/android_prebuilts_extract-tools android/prebuilts/extract-tools``


cd to the android folder and,

git clone your dt to the usual path like you would while building, like device/brand/codename

Clone the common tree also, if it exists

Check if your extract-files.sh is updated to track tools/extract-utils, if it's not, or the file itself doesn't exist,
you need to get it from GitHub, it's almost on every tree.

``bash extract-files.sh /path/to/dumpyara/working/zipname``

Wait and watch it do its thing

Once that is done, you just need to go to vendor/brand/codename and,

git init, commit and push it up!

This should be done for the common tree also which would be vendor/brand/smxx-common

Source Code
CC BY-NC-SA 4.0
  ©  2024  baalajimaestro.
Powered by 
Ghost CMS
 & 
Astro
