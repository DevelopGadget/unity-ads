# unityads

Ad Network flutter plugin unity ads

## Getting Started

``` dart
import 'package:flutter/foundation.dart';
import 'package:flutter/material.dart';
import 'dart:async';

import 'package:adsunity/adsunity.dart';

void main() => runApp(MyApp());

class MyApp extends StatefulWidget {
  @override
  _MyAppState createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> with UnityAdsListener {
  String _platformVersion = 'Unknown';

  @override
  void initState() {
    super.initState();
    UnityAds.initialize('your_android_id', 'your_ios_id', this, testMode: !kReleaseMode);
    Future.delayed(Duration(seconds: 5), () {
      UnityAds.show('video');
    });
  }

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: const Text('Plugin example app'),
        ),
        body: Center(
          child: Text('Running on: $_platformVersion\n'),
        ),
      ),
    );
  }

  @override
  void onUnityAdsError(UnityAdsError error, String message) {
    // TODO: implement onUnityAdsError
  }

  @override
  void onUnityAdsFinish(String placementId, FinishState result) {
    // TODO: implement onUnityAdsFinish
  }

  @override
  void onUnityAdsReady(String placementId) {
    // TODO: implement onUnityAdsReady
  }

  @override
  void onUnityAdsStart(String placementId) {
    // TODO: implement onUnityAdsStart
  }
}
```