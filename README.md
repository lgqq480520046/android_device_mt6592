# Build

* features

  * wifi
  * gsm (call in / call out / hangout)
  * egl
  * sound

* init

        # repo init -u git://github.com/CyanogenMod/android.git -b cm-11.0
        
        # repo sync
        
        # source build/envsetup.sh
        
        # lunch cm_mt6592-eng

* recoveries

        # . build/tools/device/makerecoveries.sh cm_mt6592-eng
    
        # mka bootimage

* full build

        # brunch cm_mt6592-eng

* system binaries

        # make framework
        # make strace

* build one java module

        # mmm packages/apps/Nfc/ || (cd packages/apps/Nfc/ && mm)

# MTK

Few words about mtk related binaries, services and migration peculiarities.

# Limitations

Services requires root:

`system/core/rootdir/init.rd`

  * surfaceflinger depends on sched_setscheduler calls, unable to change process priority from 'system' user (default user 'system')

  * mediaserver depends on /data/nvram folder access, unable to do voice calls from 'media' user (default user 'media')
