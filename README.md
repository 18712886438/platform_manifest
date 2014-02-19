[Android Open Kang Project](http://aokp.co)
====================================


Download the Source
===================

Please read the [AOSP building instructions](http://source.android.com/source/index.html) before proceeding.

Initializing Repository
-----------------------

Init core trees without any device/kernel/vendor :

    $ repo init -u https://github.com/AICP/platform_manifest.git -b kitkat-caf

Init repo with all devices, kernels and vendors supported by AICP :

    $ repo init -u https://github.com/AICP/platform_manifest.git -b kitkat-caf -g all,kernel,device,vendor

Init repo only for a particular device :

    $ repo init -u https://github.com/AICP/platform_manifest.git -b kitkat-caf -g all,-notdefault,<devicename>,<vendorname>

for example, to init only trees needed to build m7 :

    $ repo init -u https://github.com/AICP/platform_manifest.git -b kitkat-caf -g all,-notdefault,m7,htc

Init repo for multiple devices :

    $ repo init -u https://github.com/AICP/platform_manifest.git -b kitkat-caf -g all,-notdefault,<devicename1>,<devicename2>,<devicename3>,<vendorname1>,<vendorname2>,<vendorname3>

for example, to init trees needed to build m7 and endeavoru :

    $ repo init -u https://github.com/AICP/platform_manifest.git -b kitkat-caf -g all,-notdefault,m7,endeavoru,htc


sync repo :

    $ repo sync

***

Building
--------

After the sync is finished, please read the [instructions from the Android site](http://s.android.com/source/building.html) on how to build.

    . build/envsetup.sh
    brunch


You can also build (and see how long it took) for specific devices like this:

    . build/envsetup.sh
    time brunch aokp_m7-userdebug

Remember to `make clobber` every now and then!
