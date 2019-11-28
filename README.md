# android-wakelock-example
This is a sample of android wake lock to turn on the screen when it's triggered. 
        
        //import the following package
        import android.os.PowerManager;
        
        
        PowerManager powerManager = (PowerManager) getSystemService(POWER_SERVICE);
        PowerManager.WakeLock wakeLock; = powerManager.newWakeLock(PowerManager.FULL_WAKE_LOCK |
                PowerManager.ACQUIRE_CAUSES_WAKEUP |
                PowerManager.ON_AFTER_RELEASE, "app::WakeLock");

        //acquire will turn on the display
        wakeLock.acquire();

        //release will release the lock from CPU, in case of that, screen will go back to sleep mode in defined time bt device settings
        wakeLock.release();
        
        
# make sure the following line included to your manifest file.
        
         <uses-permission android:name="android.permission.WAKE_LOCK"/>
