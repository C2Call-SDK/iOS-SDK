iOS-SDK
=======

C2Call iOS7 SDK V1.0.0 B22 now available
=======

C2Call Social Communication SDK V 1.0.0 Release Notes
=======

New Features:
- Personal Status Message for users (SCUserStatusController / SCEditStatusController).
- Show Friends Status Messages in Friendlist and FriendDetails
- Online status now simplified (offline, online, online (active))
- offline - The device is not connected
- online - The device is connected, the app is in background
- online (active) - The device is connected, the user is active in the app
- New UserImage API
- [SCUserProfile currentUser].userImage
- [[SCUserProfile currentUser] setUserImage:withCompletionHandler]
- [[C2CallPhone currentPhone] largeUserImageForUserid:];
- Extended Message API 
- [[SCDataManager instance] markAsRead:(MOC2CallEvent *)]
- [[SCDataManager instance] totalMissedMessages]
- [[SCDataManager instance] totalMissedCalls]
- [[SCDataManager instance] missedCallsForContact:];
- [[SCDataManager instance] resetMissedCallsForContact:];
- Extended Group Information
- MOC2CallEvent has now a property "originalSender" which carries the userid of the original sender in a group message
- MOGroupMember has a new property "userid"
- New ViewController Components
- SCUserStatusController 
- SCEditStatusController
- SCUserImageController
- Extended Database Schema

Bugfixes:
- Support for Keyboard Toolbars in SCChatController (for example Chinese Keyboard Toolbars)
- Fixes for Addressbook handling
- Fixes for several crash scenarios

IMPORTANT NOTE:
When adding SocialCommunication.resources, two additional steps have to be done:

A NEW DATAMODEL VERSION HAS BEEN ADDED:
1. Seek for C2CallDataModel and select the current data model as: C2CallDataModel 15.xcdatamodel
Sometimes, the wrong C2CallDataModel is pre-selected, which causes a crash.

2. Please manually add the following files to your "Copy Bundle Resources" section in your Application Target Build Phases:
myshader.vsh
myshader.fsh
Just seek for myshader and drag&drop it into your "Copy Bundle Resources" section. This is important as the files will not be copied into your Application Bundle by default at compile time.
The video call does not work in this case.
3. When updating from an older version of the SDK, please check your Framework Search Path in the Build Settings and remove any path component linking to an older version of the SDK. Otherwise you might still use the old version, as XCode is linking frameworks in the order of the Framework Search Path.
