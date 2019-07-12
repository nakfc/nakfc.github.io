# Chapter One:实例

![QQ截图20190628191234.png](https://i.loli.net/2019/06/28/5d15f6496436e92335.png)

## AS+GoogleAdMob+Quick

0(strings.xml)

        <string name="admob_ad_app_id">ca-app-pub-3614081456275267~6175238021</string>
        <string name="admob_ad_unit_id">ca-app-pub-3614081456275267/2671107283</string>

        <!-- This is an ad unit ID for a test ad. Replace with your own banner ad unit id. -->
        <string name="admob_ad_unit_id_test">ca-app-pub-3940256099942544/6300978111</string>

1(project:build.gradle)

        google()

2(app:build.gradle)

        implementation 'com.google.android.gms:play-services-ads:17.2.0'
        // or
        implementation 'com.google.android.gms:play-services-ads:12.0.0'

3(AndroidManifest.xml)

        <meta-data
        android:name="com.google.android.gms.ads.APPLICATION_ID"
        android:value="@string/admob_ad_app_id"/>

4(MyActivity.java)

        private AdView mAdView;

        // onCreate()

        // Initialize the Mobile Ads SDK with admob_ad_app_id.
        MobileAds.initialize(this,"ca-app-pub-3614081456275267~6175238021");
        mAdView = findViewById(R.id.adView);
        AdRequest adRequest = new AdRequest.Builder().build();
        // AdRequest adRequest = new AdRequest.Builder().addTestDevice(AdRequest.DEVICE_ID_EMULATOR).build();
        mAdView.loadAd(adRequest);

5(activity_my.xml)

        <com.google.android.gms.ads.AdView
                xmlns:ads="http://schemas.android.com/apk/res-auto"
                android:id="@+id/adView"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_centerHorizontal="true"
                android:layout_alignParentBottom="true"
                ads:adSize="BANNER"
                ads:adUnitId="@string/admob_ad_unit_id_test">
        </com.google.android.gms.ads.AdView>