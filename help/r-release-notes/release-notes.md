---
description: These release notes provide information about features, enhancements, fixes, and known issues for each Target Standard and Target Premium release.
keywords: Release notes;prerelease
seo-description: These release notes provide information about features, enhancements, fixes, and known issues for each Adobe Target Standard and Target Premium release.
seo-title: Adobe Target release notes (current)
solution: Target
title: Target release notes (current)
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
---

# Target release notes (current){#target-release-notes-current}

These release notes provide information about features, enhancements, and fixes for each Target Standard and Target Premium release.

## Announcements

**July 31, 2019**

[!UICONTROL Enterprise Permissions] allows [!DNL Target] customers to use a single organization, but divide it into workspaces for different teams or workflows. The [!UICONTROL Enterprise Permissions] feature facilitates effective scaling of optimization programs across teams. Although this feature was available in the [!DNL Target] UI, the Admin APIs lacked the corresponding support until the [!DNL Target] February 2019 release. Adobe updated the Admin APIs so that you can use the integration account to access all workspaces created in your organization. So, while earlier, Admin APIs were restricted to the default workspace, the February 2019 update granted access to all workspaces with [!UICONTROL Approver] access.

With the upcoming [!DNL Target] September 2019 release, [!UICONTROL Enterprise Permissions] will provide customers with the following access controls:

* You can choose the workspaces to which the integration can be applied
* You can apply a role to the Adobe I/O integration: [!UICONTROL Approver], [!UICONTROL Editor], or [!UICONTROL Observer].

**Action Required**: Customers who are currently leveraging APIs for CRUD operations on resources (activities, audiences, offers, and reporting) across all workspaces need to grant their existing Adobe I/O integration access to all workspaces with the desired role. Prior to the September release, all integrations operated using [!UICONTROL Approver] access, regardless of the role selected from the [!UICONTROL Product Role] drop-down list. With the upcoming release, you can now select the desired role. 

This action should be performed during the month of **August 2019**. After the [!DNL Target] September 2019 release, the access controls will activate and you will observe access to just the default workspace if that's how you are currently set up. There is no adverse consequence to setting up integration roles in advance.

For step-by-step instructions and more information, see [Grant Adobe I/O integrations access to workspaces and assign roles](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md).

## Target Mobile VEC SDK iOS 2.1.0 & Android 1.1.1 (August 7, 2019)

This release of Mobile VEC SDK includes the following enhancements and fixes:

(The issue numbers in parentheses are for internal Adobe use.)

* Added support for Preview for Visual Activities on mobile device. (TGT-27875)
* Fixed an issue that caused an Apple Standard violation due to `UIImagePickerController` usage.
* Removed GSON dependency from Android SDK. (TGT-31710)
* Removed Other redundant Gradle dependencies (TGT-35479)
* Fixed an issue that caused the delivery offer to not reset at the time of authoring. (TGT-35270)

## Target Standard/Premium 19.7.1 (July 24, 2019) {#tgt-19-7-1}

This release includes the following new features and enhancements:

(The issue numbers in parentheses are for internal Adobe use.)

|Feature / Enhancement|Description|
| --- | --- |
|Mobile App Visual Experience Composer|A new Modifications panel displays in the Mobile App VEC that displays the elements you have set up for click-tracking. (TGT-31741)<br> See [Set up click tracking in the Mobile App](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md).|
|![Premium badge](/help/assets/premium.png)<br>Recommendations in A/B Test and Experience Targeting (XT) activities|The Recommendations offer (algorithm) status displays on the Overview page for A/B Test and XT activities that contain Recommendations offers. Statuses include: Results Ready, Results Not Ready, and Feed Failure. (TGT-33649)<br>See [Recommendations as an offer](/help/c-recommendations/recommendations-as-an-offer.md#status).|
|Cross-domain tracking support for at.js 2.0+ via the Experience Cloud ID  (ECID) library|Previously, cross-domain tracking was not supported in at.js 2.*x*. With this release, customers using at.js 2.0 or above can now utilize cross-domain tracking through the ECID library. The ECID library must be installed on the page in conjunction with at.js 2.0 or above in order for cross-domain tracking to work. [Experience Cloud ID library 4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) must be used.<br>See [Cross-domain tracking support in at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md#cross-domain).|
|Target support for Apple’s ITP 2.1 and ITP 2.2 via the Experience Cloud ID (ECID) library 4.3|Today, Target customers can mitigate Apple's ITP 2.1 and ITP 2.2 by leveraging Adobe’s CNAME certification program.<br>With this release, Target introduces a seamless integration with the ECID library 4.3, which leverages a server-side cookie to mitigate ITP 2.1 and ITP 2.2. It is highly recommended that Target customers deploy [ECID library 4.3+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) in conjunction with Target’s JavaScript library to mitigate any future ITP releases. The ECID library will continue to roll out enhancements that provide a robust solution to the ever-changing cookie policies introduced by browsers.<br>See [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).|

**Enhancement, fixes, and changes**

* Fixed an issue that prevented exclusion values in Recommendations activities from being cleared when adding duplicate values. (TGT-34996)
* You can now remove a design in a Recommendations activity from the Targeting page (Step 2 of the three-part guided workflow). Note that to remove a design, there must be more than one design selected. (TGT-35118)
* Fixed an issue that prevented custom criteria cards for some customers to load properly in the Target UI or to be editable. (TGT-35170)

## at.js version 2.1.1 (July 24, 2019)

This release of at.js is a maintenance release and includes the following enhancements and fixes:

(The issue numbers in parentheses are for internal Adobe use.)

* Fixed an issue that caused multiple beacons to fire when using the Click Tracking metric on the Goals & Settings page in the Visual Experience Composer (VEC). (TNT-32812)
* Fixed an issue that caused `triggerView()` to not render offers more than once. (TNT-32780)
* Fixed an issue with `triggerView()` to ensure that the request contains Marketing Cloud ID (MCID) information. (TNT-32776)
* Fixed an issue that prevented the `triggerView()` notification to fire even if there are no saved views. (TNT-32614)
* Fixed an issue that caused an error due to the use of decodeURIcomponent that caused issues when the URL contains a malformed query string parameter. (TNT-32710)
* The beacon flag is now set to "true" in the context of delivery requests sent via the `Navigator.sendBeacon()` API. (TNT-32683)
* Fixed an issue that prevented Recommendations offers from displaying on websites for a few customers. Customers could see the offer content in the delivery API call but the offer was not applied on the website. (TNT-32680)
* Fixed an issue that caused click-tracking across multiple experiences to not work as expected. (TNT-32644)
* Fixed an issue that prevented at.js from applying the second metric after the rendering of the first metric fails. (TNT-32628)
* Fixed an issue when passing `mboxThirdPartyId` using the `targetPageParams` function that caused the request payload to not be present in either the query parameters or in the request payload. (TNT-32613)
* Fixed an issue that caused display and click notification responses to be blocked in Chromium-based browsers (including Google Chrome). (TNT-32290)

For information about this and previous versions of at.js, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## Documentation Changes, Past Release Notes, and Experience Cloud Release Notes {#section_1BC5F5208DA548E9B4344A0836E4B943}

In addition to the notes for each release, the following resources provide additional information:

|Resource|Details|
|--- |--- |
|Documentation changes|View detailed information about updates to this guide that might not be included in these release notes.<br>For more information, see [Documentation Changes](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C).|
|Release notes for previous releases|View information about new features and enhancements in previous releases of Target Standard and Target Premium.<br>For more information, see [Release notes for previous releases](../r-release-notes/release-notes-for-previous-releases.md).|
|Adobe Experience Cloud release notes|View the latest release notes for the Adobe Experience Cloud solutions.<br>For more information, see [Experience Cloud Release Notes](https://marketing.adobe.com/resources/help/en_US/whatsnew/).|

## Prerelease Information {#section_5D588F0415A2435B851A4D0113ACA3A0}

The following resources let you see what's coming in the next Target release.

|Resource|Details|
|--- |--- |
|Adobe Priority Product Update list|To receive advance notifications about upcoming product enhancements to Target and other Adobe Experience Cloud solutions, sign up for the Adobe Priority Product Update:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)|
|Upcoming release notes|For information about the current month's Target releases, including prerelease information, see the [Target Release Notes - Prerelease](/help/r-release-notes/target-release-notes.md) page.|
