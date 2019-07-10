# Importing the Mobile Ads SDK
## Banner Ads In Android
![QQ截图20190628191234.png](https://i.loli.net/2019/06/28/5d15f6496436e92335.png)

### Android Studio(Importing)
1. Add gradle dependency(build.gradle)

        dependencies{
            compile 'com.android.support:appcompat-v7:23.1.1'
            compile 'com.google.android.gms:play-services-ads:8.3.0'
        }

2. Do a gradle sync(MainActivity.java) 

        // onCreate()
        AdView adView = (AdView)findViewById(R.id.adView);

### Android Studio(Start)
1. Place an AdView(activity_main.xml)

        <com.google.android.gms.ads.AdView
            android:id="@+id/adView"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_centerHorizontal="true"
            android:layout_alignParentBottom="true"
            ads:adSize="BANNER"
            ads:adUnitId="ca-app-pub-2739847298347289743/23842374>
        </com.google.android.gms.ads.AdView>

2. Build a request(MainActivity.java)

        AdRequesst adRequest = new AdRequest.Builder()
            .addTestDevice(AdRequest.DEVICE_ID_EMULATOR)
            .build();

3. Load an ad(MainActivity.java)

        adView.loadAd(adRequest);

## Interstitial Ads In Android
 1. Create InterstitialAd object(MainActivity.java)
 
         private InterstitialAd mInterstitial;
       
         // onCreate()
         mInterstitial = new InterstitialAd(this);
         mInterstitial.setAdUnityI("ca-app-pub-12123123123123/101201020");
         
 2. Request an ad(MainActivity.java)
 
         AdRequest request = new AdRequest.Builder().addTestDevice(AdRequest.DEVICE_ID_EMULATOR).build();
         mInterstitial.loadAd(request);
 3. Wait until the right moment
 4. Check if the ad has loaded,Display ad(MainActivity.java)
 
         private InterstitialAd mInterstitial;
       
         // onClick()
         if(mInterstitial.isLoaded){
           mInterstitial.show();
         }

# AdMob With **Firebase**

1. Link AdMob app to Firebase

2. Download google-serivces.json

3. Configure gradle plugin

4. Add individual services

# Reward Video
1. Add gradle dependency(build.gradle)
dependencies{
    implementation 'com.google.android.gms
}
