---
slug: downloading-timeline-from-twitter
redirect_from: "/article/892-download-timeline"
title: Downloading Timeline from Twitter
---
This task will download every tweet from your timeline.

## Settings
### Connection
_Required_  
The Twitter connection to use. See the [Twitter](twitter) article if you require more information on how to create/manage connections.

### Output File
_Required_  
The name of the file to output the data to.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<Tweets>
  <Tweet>
    <Id>763384034340773889</Id>
    <IdStr>763384034340773889</IdStr>
    <InReplyToUserId />
    <InReplyToStatusId />
    <InReplyToScreenName />
    <IsTruncated>false</IsTruncated>
    <IsFavorited>false</IsFavorited>
    <FavoriteCount>9</FavoriteCount>
    <IsRetweeted>false</IsRetweeted>
    <RetweetCount>10</RetweetCount>
    <Text>Almost time. #VSLive is kicking off in a few minutes. Next up: #Windows for Makers: #RaspberryPi, #Arduino &amp; #IoT. https://t.co/jzkzqFj61e</Text>
    <TextAsHtml>Almost time. <a href="https://twitter.com/search?q=%23VSLive" target="_blank">#VSLive</a> is kicking off in a few minutes. Next up: <a href="https://twitter.com/search?q=%23Windows" target="_blank">#Windows</a> for Makers: <a href="https://twitter.com/search?q=%23RaspberryPi" target="_blank">#RaspberryPi</a>, <a href="https://twitter.com/search?q=%23Arduino" target="_blank">#Arduino</a> &amp; <a href="https://twitter.com/search?q=%23IoT" target="_blank">#IoT</a>. <a href="https://t.co/jzkzqFj61e" target="_blank">https://t.co/jzkzqFj61e</a></TextAsHtml>
    <TextDecoded>Almost time. #VSLive is kicking off in a few minutes. Next up: #Windows for Makers: #RaspberryPi, #Arduino & #IoT. https://t.co/jzkzqFj61e</TextDecoded>
    <Author>
      <Id>16913772</Id>
      <FollowersCount>373134</FollowersCount>
      <Name>Visual Studio</Name>
      <Description>Follow us for the latest Microsoft Visual Studio news and related information for developers.</Description>
      <ProfileImageUrl>http://pbs.twimg.com/profile_images/505104774153256960/SR2hUhQN_normal.png</ProfileImageUrl>
      <Url>http://t.co/OqnL9IGcUY</Url>
      <IsProtected>false</IsProtected>
      <ScreenName>VisualStudio</ScreenName>
      <Location>Redmond, WA, USA</Location>
      <Status />
      <FriendsCount>930</FriendsCount>
      <ProfileBackgroundColor>68217A</ProfileBackgroundColor>
      <UtcOffset>-25200</UtcOffset>
      <ProfileTextColor>1F222B</ProfileTextColor>
      <ProfileBackgroundImageUrl>http://pbs.twimg.com/profile_background_images/378800000117002036/51fcdb17ec1e080aa852086bcfbdd1a1.gif</ProfileBackgroundImageUrl>
      <TimeZone>Pacific Time (US & Canada)</TimeZone>
      <FavouritesCount>405</FavouritesCount>
      <ListedCount>4610</ListedCount>
      <ProfileLinkColor>68217A</ProfileLinkColor>
      <StatusesCount>21994</StatusesCount>
      <ProfileSidebarFillColor>FFFFFF</ProfileSidebarFillColor>
      <ProfileSidebarBorderColor>FFFFFF</ProfileSidebarBorderColor>
      <IsProfileBackgroundTiled>false</IsProfileBackgroundTiled>
      <IsVerified>true</IsVerified>
      <IsGeoEnabled>true</IsGeoEnabled>
      <Language>en</Language>
      <CreatedDate>2008-10-22T22:01:24Z</CreatedDate>
      <FollowRequestSent>false</FollowRequestSent>
      <IsTranslator>false</IsTranslator>
      <ContributorsEnabled>false</ContributorsEnabled>
      <ProfileBackgroundImageUrlHttps>https://pbs.twimg.com/profile_background_images/378800000117002036/51fcdb17ec1e080aa852086bcfbdd1a1.gif</ProfileBackgroundImageUrlHttps>
      <ProfileImageUrlHttps>https://pbs.twimg.com/profile_images/505104774153256960/SR2hUhQN_normal.png</ProfileImageUrlHttps>
      <IsDefaultProfile>false</IsDefaultProfile>
      <RawSource />
    </Author>
    <Source><a href="http://www.sprinklr.com" rel="nofollow">Sprinklr</a></Source>
    <User>
      <Id>16913772</Id>
      <FollowersCount>373134</FollowersCount>
      <Name>Visual Studio</Name>
      <Description>Follow us for the latest Microsoft Visual Studio news and related information for developers.</Description>
      <ProfileImageUrl>http://pbs.twimg.com/profile_images/505104774153256960/SR2hUhQN_normal.png</ProfileImageUrl>
      <Url>http://t.co/OqnL9IGcUY</Url>
      <IsProtected>false</IsProtected>
      <ScreenName>VisualStudio</ScreenName>
      <Location>Redmond, WA, USA</Location>
      <Status />
      <FriendsCount>930</FriendsCount>
      <ProfileBackgroundColor>68217A</ProfileBackgroundColor>
      <UtcOffset>-25200</UtcOffset>
      <ProfileTextColor>1F222B</ProfileTextColor>
      <ProfileBackgroundImageUrl>http://pbs.twimg.com/profile_background_images/378800000117002036/51fcdb17ec1e080aa852086bcfbdd1a1.gif</ProfileBackgroundImageUrl>
      <TimeZone>Pacific Time (US & Canada)</TimeZone>
      <FavouritesCount>405</FavouritesCount>
      <ListedCount>4610</ListedCount>
      <ProfileLinkColor>68217A</ProfileLinkColor>
      <StatusesCount>21994</StatusesCount>
      <ProfileSidebarFillColor>FFFFFF</ProfileSidebarFillColor>
      <ProfileSidebarBorderColor>FFFFFF</ProfileSidebarBorderColor>
      <IsProfileBackgroundTiled>false</IsProfileBackgroundTiled>
      <IsVerified>true</IsVerified>
      <IsGeoEnabled>true</IsGeoEnabled>
      <Language>en</Language>
      <CreatedDate>2008-10-22T22:01:24Z</CreatedDate>
      <FollowRequestSent>false</FollowRequestSent>
      <IsTranslator>false</IsTranslator>
      <ContributorsEnabled>false</ContributorsEnabled>
      <ProfileBackgroundImageUrlHttps>https://pbs.twimg.com/profile_background_images/378800000117002036/51fcdb17ec1e080aa852086bcfbdd1a1.gif</ProfileBackgroundImageUrlHttps>
      <ProfileImageUrlHttps>https://pbs.twimg.com/profile_images/505104774153256960/SR2hUhQN_normal.png</ProfileImageUrlHttps>
      <IsDefaultProfile>false</IsDefaultProfile>
      <RawSource />
    </User>
    <RetweetedStatus />
    <CreatedDate>2016-08-10T14:38:31Z</CreatedDate>
    <Location />
    <Language>en</Language>
    <Entities />
    <ExtendedEntities />
    <IsPossiblySensitive>false</IsPossiblySensitive>
    <Place />
  </Tweet>
</Tweets>
```