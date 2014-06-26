iOS-SDK
=======

C2Call iOS7 SDK SDK V 1.1.1 now available
=======

C2Call Social Communication SDK V 1.1.1 Release Notes

New Features:
- Partitial SourceCode release of the most important SDK ViewController components
- New API Calls
    - C2CallPhone: shareMessageOnFacebook
    - C2CallPhone: activeMembersInCallForGroup
    - C2CallPhone: activeVideoCallForGroup
    - C2CallPhone: isGroupUser
    - C2CallPhone: canEncryptMessageForTarget
    - C2CallPhone: queryPriceForNumber
    - C2CallPhone: setDefaultCountryCode
    - C2CallPhone: setDefaultAreaCode
    - C2CallPhone: loadGroupHistory
    - C2CallPhone: downloadStatusForKey
    - C2CallPhone: failedDownloadStatusForKey
    - C2CallPhone: getApplicationCredits
    - C2CallPhone: redeemVoucher
    - C2CallPhone: redeemApplicationVoucher
    - C2CallPhone: chargeApplicationCredit
    - SIPPhone: isValidNumber
    - SCUserProfile: useFacebook
    - SCDataManager: recentContacts
- Several Bugfixes

IMPORTANT NOTE:
When adding SocialCommunication.resources, two additional steps have to be done:

A NEW DATAMODEL VERSION HAS BEEN ADDED:
1. Seek for C2CallDataModel and select the current data model as: C2CallDataModel 17.xcdatamodel
Sometimes, the wrong C2CallDataModel is pre-selected, which causes a crash.

2. Please manually add the following files to your "Copy Bundle Resources" section in your Application Target Build Phases:
    myshader.vsh
    myshader.fsh
Just seek for myshader and drag&drop it into your "Copy Bundle Resources" section. This is important as the files will not be copied into your Application Bundle by default at compile time.
The video call does not work in this case.
3. When updating from an older version of the SDK, please check your Framework Search Path in the Build Settings and remove any path component linking to an older version of the SDK. Otherwise you might still use the old version, as XCode is linking frameworks in the order of the Framework Search Path.

