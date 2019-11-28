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
         
# Full Source Code is Here

        package com.example.wakelocksample;

        import androidx.appcompat.app.AppCompatActivity;
        import android.os.Bundle;
        import android.os.PowerManager;
        import org.w3c.dom.Text;

        public class MainActivity extends AppCompatActivity {

         PowerManager.WakeLock wakeLock;
         @Override
         protected void onCreate(Bundle savedInstanceState) {
         super.onCreate(savedInstanceState);
         setContentView(R.layout.activity_main);


        PowerManager powerManager = (PowerManager) getSystemService(POWER_SERVICE);
        wakeLock = powerManager.newWakeLock(PowerManager.FULL_WAKE_LOCK |
                PowerManager.ACQUIRE_CAUSES_WAKEUP |
                PowerManager.ON_AFTER_RELEASE, "app::WakeLock");

        //acquire will turn on the display
        wakeLock.acquire();

        //release will release the lock from CPU, in case of that, screen will go back to sleep mode in defined time bt device settings
        wakeLock.release();


        }
        }
