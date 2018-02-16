---
slug: downloading-mentions-from-twitter
redirect_from: "/article/890-download-mentions"
title: Downloading Mentions from Twitter
---
This task will download any mentions that you have on Twitter. A mentions is when somebody tags you in a tweet.

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
<Mentions>
  <Mention>
    <Id>372727666199130114</Id>
    <IdStr>372727666199130114</IdStr>
    <InReplyToUserId />
    <InReplyToStatusId />
    <InReplyToScreenName />
    <IsTruncated>false</IsTruncated>
    <IsFavorited>false</IsFavorited>
    <FavoriteCount>0</FavoriteCount>
    <IsRetweeted>false</IsRetweeted>
    <RetweetCount>1</RetweetCount>
    <Text>We've just used @zynk for the first time to import order data into Sage for a client. It's so powerful yet very simple/logical to use.</Text>
    <TextAsHtml>We've just used <a href="https://twitter.com/zynk" target="_blank">@zynk</a> for the first time to import order data into Sage for a client. It's so powerful yet very simple/logical to use.</TextAsHtml>
    <TextDecoded>We've just used @zynk for the first time to import order data into Sage for a client. It's so powerful yet very simple/logical to use.</TextDecoded>
    <Author>
      <Id>39217889</Id>
      <FollowersCount>929</FollowersCount>
      <Name>Bluelinemedia</Name>
      <Description>Gloucestershire's leading web agency offering web design, bespoke software and marketing since 2001 - Call us on 01242 244620</Description>
      <ProfileImageUrl>http://pbs.twimg.com/profile_images/1731587124/bluelinemedia-cheltenham-web-design_normal.jpg</ProfileImageUrl>
      <Url>http://t.co/20zEYv14aJ</Url>
      <IsProtected>false</IsProtected>
      <ScreenName>blmuk</ScreenName>
      <Location>Cheltenham, UK</Location>
      <Status />
      <FriendsCount>1361</FriendsCount>
      <ProfileBackgroundColor>C0DEED</ProfileBackgroundColor>
      <UtcOffset>3600</UtcOffset>
      <ProfileTextColor>333333</ProfileTextColor>
      <ProfileBackgroundImageUrl>http://pbs.twimg.com/profile_background_images/638820383/kzdrbo46w74btzn2ngwi.jpeg</ProfileBackgroundImageUrl>
      <TimeZone>London</TimeZone>
      <FavouritesCount>4</FavouritesCount>
      <ListedCount>41</ListedCount>
      <ProfileLinkColor>0084B4</ProfileLinkColor>
      <StatusesCount>1439</StatusesCount>
      <ProfileSidebarFillColor>DDEEF6</ProfileSidebarFillColor>
      <ProfileSidebarBorderColor>C0DEED</ProfileSidebarBorderColor>
      <IsProfileBackgroundTiled>false</IsProfileBackgroundTiled>
      <IsVerified>false</IsVerified>
      <IsGeoEnabled>true</IsGeoEnabled>
      <Language>en</Language>
      <CreatedDate>2009-05-11T08:40:39Z</CreatedDate>
      <FollowRequestSent>false</FollowRequestSent>
      <IsTranslator>false</IsTranslator>
      <ContributorsEnabled>false</ContributorsEnabled>
      <ProfileBackgroundImageUrlHttps>https://pbs.twimg.com/profile_background_images/638820383/kzdrbo46w74btzn2ngwi.jpeg</ProfileBackgroundImageUrlHttps>
      <ProfileImageUrlHttps>https://pbs.twimg.com/profile_images/1731587124/bluelinemedia-cheltenham-web-design_normal.jpg</ProfileImageUrlHttps>
      <IsDefaultProfile>false</IsDefaultProfile>
      <RawSource />
    </Author>
    <Source><a href="http://twitter.com" rel="nofollow">Twitter Web Client</a></Source>
    <User>
      <Id>39217889</Id>
      <FollowersCount>929</FollowersCount>
      <Name>Bluelinemedia</Name>
      <Description>Gloucestershire's leading web agency offering web design, bespoke software and marketing since 2001 - Call us on 01242 244620</Description>
      <ProfileImageUrl>http://pbs.twimg.com/profile_images/1731587124/bluelinemedia-cheltenham-web-design_normal.jpg</ProfileImageUrl>
      <Url>http://t.co/20zEYv14aJ</Url>
      <IsProtected>false</IsProtected>
      <ScreenName>blmuk</ScreenName>
      <Location>Cheltenham, UK</Location>
      <Status />
      <FriendsCount>1361</FriendsCount>
      <ProfileBackgroundColor>C0DEED</ProfileBackgroundColor>
      <UtcOffset>3600</UtcOffset>
      <ProfileTextColor>333333</ProfileTextColor>
      <ProfileBackgroundImageUrl>http://pbs.twimg.com/profile_background_images/638820383/kzdrbo46w74btzn2ngwi.jpeg</ProfileBackgroundImageUrl>
      <TimeZone>London</TimeZone>
      <FavouritesCount>4</FavouritesCount>
      <ListedCount>41</ListedCount>
      <ProfileLinkColor>0084B4</ProfileLinkColor>
      <StatusesCount>1439</StatusesCount>
      <ProfileSidebarFillColor>DDEEF6</ProfileSidebarFillColor>
      <ProfileSidebarBorderColor>C0DEED</ProfileSidebarBorderColor>
      <IsProfileBackgroundTiled>false</IsProfileBackgroundTiled>
      <IsVerified>false</IsVerified>
      <IsGeoEnabled>true</IsGeoEnabled>
      <Language>en</Language>
      <CreatedDate>2009-05-11T08:40:39Z</CreatedDate>
      <FollowRequestSent>false</FollowRequestSent>
      <IsTranslator>false</IsTranslator>
      <ContributorsEnabled>false</ContributorsEnabled>
      <ProfileBackgroundImageUrlHttps>https://pbs.twimg.com/profile_background_images/638820383/kzdrbo46w74btzn2ngwi.jpeg</ProfileBackgroundImageUrlHttps>
      <ProfileImageUrlHttps>https://pbs.twimg.com/profile_images/1731587124/bluelinemedia-cheltenham-web-design_normal.jpg</ProfileImageUrlHttps>
      <IsDefaultProfile>false</IsDefaultProfile>
      <RawSource />
    </User>
    <RetweetedStatus />
    <CreatedDate>2013-08-28T14:29:35Z</CreatedDate>
    <Location />
    <Language>en</Language>
    <Entities />
    <ExtendedEntities />
    <IsPossiblySensitive />
    <Place />
  </Mention>
</Mentions>
```