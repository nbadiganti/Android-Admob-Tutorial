
Sample App with both Banner and Full screen apps.
Download the APK and try : https://github.com/nbadiganti/Admob-Android/blob/master/app-debug-unaligned.apk?raw=true

## Android Admob ads 

Maximize your earnings with the new AdMob improved tools to help app developers build their business. I  create a simple view that launches an Interstitial on start and show a single banner advertisement. 

### Integrating the play services with the android project. 
Add the below dependency to your build.gradle file. 
`compile 'com.google.android.gms:play-services:6.5.87'`

Add the permission to your manifest file 

`<android
      android:name="com.google.android.gms.version"
      android:value="@integer/google_play_services_version" />`


Add AdActivity to launch the add in your application. 

        `<activity
            android:name="com.google.android.gms.ads.AdActivity"
            android:configChanges="keyboard|keyboardHidden|orientation|screenLayout|uiMode|screenSize|smallestScreenSize" />
`

Creating AD in the admob account,

![ad in ADMOB](https://lh3.googleusercontent.com/Z9qxloY7dbS2bACrn73ylfItWYTSM1cEL6YwybP2kjU=w1202-h832-no)

## Banner Ad

Add this to your xml 

` <com.google.android.gms.ads.AdView
        android:id="@+id/adMob"
        ads:adSize="BANNER"
        ads:adUnitId="Your Code"
        android:layout_width="fill_parent"
        android:layout_height="wrap_content"
        android:layout_alignParentTop="true" />`

Add this to your java file. 

`AdView adView = (AdView) findViewById(R.id.adMob);
        final TelephonyManager tm = (TelephonyManager) getBaseContext().getSystemService(Context.TELEPHONY_SERVICE);`

        `String deviceid = tm.getDeviceId();

        AdRequest adRequest = new AdRequest.Builder()
                .addTestDevice(AdRequest.DEVICE_ID_EMULATOR)// This is for emulators
                        //test mode on DEVICE (this example code must be replaced with your device uniquq ID)
                .addTestDevice(deviceid) // Nexus 5
                .build();
        adView.loadAd(adRequest);`

## Interstitial Ad

Add this code to your JAVA file. 

`interstitial = new InterstitialAd(this);
        // Insert the Ad Unit ID
        interstitial.setAdUnitId("ca-app-pub-XXXXXXXX");


        // Request for Ads
        AdRequest adRequest = new AdRequest.Builder()
                // Add a test device to show Test Ads
                .addTestDevice(AdRequest.DEVICE_ID_EMULATOR)
                .addTestDevice(deviceid)
                .build();


        // Load ads into Interstitial Ads
        interstitial.loadAd(adRequest);`


Enjoy! Happy coding :) 

        
   
