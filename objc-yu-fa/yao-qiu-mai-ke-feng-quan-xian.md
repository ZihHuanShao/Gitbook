# 要求麥克風權限

記得`.plist`要加入`Privacy - Microphone Usage Description`權限

```swift
#include <AVFoundation/AVFoundation.h>

...

AVAudioSessionRecordPermission permissionStatus = [[AVAudioSession sharedInstance] recordPermission];

switch (permissionStatus) {
     case AVAudioSessionRecordPermissionUndetermined:{
          [[AVAudioSession sharedInstance] requestRecordPermission:^(BOOL granted) {
          // CALL YOUR METHOD HERE - as this assumes being called only once from user interacting with permission alert!
              if (granted) {
                  // Microphone enabled code
              }
              else {
                  // Microphone disabled code
              }
           }];
          break;
          }
     case AVAudioSessionRecordPermissionDenied:
          // direct to settings...
          break;
     case AVAudioSessionRecordPermissionGranted:
          // mic access ok...
          break;
     default:
          // this should not happen.. maybe throw an exception.
          break;
}
```

## Ref.

{% embed url="https://stackoverflow.com/questions/33065150/how-to-detect-user-giving-microphone-permission-on-ios?rq=1" %}



