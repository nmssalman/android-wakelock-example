# android-wakelock-example
This is a sample of android wake lock to turn on the screen when it's triggered. 

      
        PowerManager powerManager = (PowerManager) getSystemService(POWER_SERVICE);
        wakeLock = powerManager.newWakeLock(PowerManager.FULL_WAKE_LOCK |
                PowerManager.ACQUIRE_CAUSES_WAKEUP |
                PowerManager.ON_AFTER_RELEASE, "app::WakeLock");

        //acquire will turn on the display
        wakeLock.acquire();

        //release will release the lock from CPU, in case of that, screen will go back to sleep mode in defined time bt device settings
        wakeLock.release();
        
        
# make sure the following lines on android manifest.
        
         <uses-permission android:name="android.permission.WAKE_LOCK"/>
