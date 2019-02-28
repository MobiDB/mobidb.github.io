# Android 4.4 SD Card workaround #

Unfortunately, since Android 4.4 (KitKat), apps cannot store data on the SD Card like they used to. Android apps can still read SD card data, but they can only write data to their own dedicated folder.

If you would like to save and store your data on SD Card, make sure you created the following folder structure on your SD card and specify it as a path to save your data to:


**Android/data/com.perpetuumsoft.mobidb** (if you are using a full MobiDB version)

**Android/data/com.perpetuumsoft.mobidb.lite** (if you are using a Lite version)
