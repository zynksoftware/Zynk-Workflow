---
slug: downloading-followers-from-twitter
redirect_from: "/article/888-download-followers"
title: Downloading Followers from Twitter
---
This task will download all of your active followers from Twitter.

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
<Followers>
  <Follower>
    <Id>580005650</Id>
    <FollowersCount>1091</FollowersCount>
    <Name>Test</Name>
    <Description>Quickly and accurately capture data from documents such as statements, invoices and receipts. Eliminate the need for manual data entry today.</Description>
    <ProfileImageUrl>http://pbs.twimg.com/profile_images/751384996125020160/C0SujFVc_normal.jpg</ProfileImageUrl>
    <Url>http://t.co/JIlttDns</Url>
    <IsProtected>false</IsProtected>
    <ScreenName>TestSoftware</ScreenName>
    <Location></Location>
    <Status>
      <Id>758330960685522944</Id>
      <IdStr>758330960685522944</IdStr>
      <InReplyToUserId />
      <InReplyToStatusId />
      <InReplyToScreenName />
      <IsTruncated>false</IsTruncated>
      <IsFavorited>false</IsFavorited>
      <FavoriteCount>0</FavoriteCount>
      <IsRetweeted>false</IsRetweeted>
      <RetweetCount>2</RetweetCount>
      <Text>RT @TestSoftware: AutoEntry automates data entry by capturing all of your bills, 
invoices, receipts &amp; statements #SageSummit https://t.co&hellip;</Text>
      <TextAsHtml>RT <a href="https://twitter.com/TestSoftware" target="_blank">@TestSoftware</a>: AutoEntry automates data entry by capturing all of your bills, 
invoices, receipts &amp; statements <a href="https://twitter.com/search?q=SageSummit" target="_blank">#SageSummit</a> https://t.co<a href="https://cards.twitter.com/cards/18ce53xpe8k/1xtz8" target="_blank">https://t.co/4NCYsWJ0x1</a></TextAsHtml>
      <TextDecoded>RT @TestSoftware: AutoEntry automates data entry by capturing all of your bills, 
invoices, receipts & statements #SageSummit https://t.co&hellip;</TextDecoded>
      <Author />
      <Source><a href="http://twitter.com" rel="nofollow">Twitter Web Client</a></Source>
      <User />
      <RetweetedStatus>
        <Id>757967560830623744</Id>
        <IdStr>757967560830623744</IdStr>
        <InReplyToUserId />
        <InReplyToStatusId />
        <InReplyToScreenName />
        <IsTruncated>false</IsTruncated>
        <IsFavorited>false</IsFavorited>
        <FavoriteCount>2</FavoriteCount>
        <IsRetweeted>false</IsRetweeted>
        <RetweetCount>2</RetweetCount>
        <Text>AutoEntry automates data entry by capturing all of your bills, 
invoices, receipts &amp; statements #SageSummit https://t.co/4NCYsWJ0x1</Text>
        <TextAsHtml>AutoEntry automates data entry by capturing all of your bills, 
invoices, receipts &amp; statements <a href="https://twitter.com/search?q=SageSummit" target="_blank">#SageSummit</a> <a href="https://cards.twitter.com/cards/18ce53xpe8k/1xtz8" target="_blank">https://t.co/4NCYsWJ0x1</a></TextAsHtml>
        <TextDecoded>AutoEntry automates data entry by capturing all of your bills, 
invoices, receipts & statements #SageSummit https://t.co/4NCYsWJ0x1</TextDecoded>
        <Author />
        <Source><a href="https://ads.twitter.com" rel="nofollow">Twitter Ads</a></Source>
        <User />
        <RetweetedStatus />
        <CreatedDate>2016-07-26T15:55:23Z</CreatedDate>
        <Location />
        <Language>en</Language>
        <Entities>
          <Text>SageSummit</Text>
          <Indices>100</Indices>
          <Indices>111</Indices>
          <EntityType>0</EntityType>
          <StartIndex>100</StartIndex>
          <EndIndex>111</EndIndex>
        </Entities>
        <Entities>
          <Value>https://t.co/4NCYsWJ0x1</Value>
          <ExpandedValue>https://cards.twitter.com/cards/18ce53xpe8k/1xtz8</ExpandedValue>
          <DisplayUrl>cards.twitter.com/cards/18ce53xp&hellip;</DisplayUrl>
          <Indices>112</Indices>
          <Indices>135</Indices>
          <EntityType>2</EntityType>
          <StartIndex>112</StartIndex>
          <EndIndex>135</EndIndex>
        </Entities>
        <ExtendedEntities />
        <IsPossiblySensitive>false</IsPossiblySensitive>
        <Place />
        <RawSource />
      </RetweetedStatus>
      <CreatedDate>2016-07-27T15:59:24Z</CreatedDate>
      <Location />
      <Language>en</Language>
      <Entities>
        <Id>580005650</Id>
        <ScreenName>TestSoftware</ScreenName>
        <Name>Test</Name>
        <Indices>3</Indices>
        <Indices>17</Indices>
        <EntityType>1</EntityType>
        <StartIndex>3</StartIndex>
        <EndIndex>17</EndIndex>
      </Entities>
      <Entities>
        <Text>SageSummit</Text>
        <Indices>119</Indices>
        <Indices>130</Indices>
        <EntityType>0</EntityType>
        <StartIndex>119</StartIndex>
        <EndIndex>130</EndIndex>
      </Entities>
      <Entities>
        <Value>https://t.co/4NCYsWJ0x1</Value>
        <ExpandedValue>https://cards.twitter.com/cards/18ce53xpe8k/1xtz8</ExpandedValue>
        <DisplayUrl>cards.twitter.com/cards/18ce53xp&hellip;</DisplayUrl>
        <Indices>143</Indices>
        <Indices>144</Indices>
        <EntityType>2</EntityType>
        <StartIndex>143</StartIndex>
        <EndIndex>144</EndIndex>
      </Entities>
      <ExtendedEntities />
      <IsPossiblySensitive>false</IsPossiblySensitive>
      <Place />
      <RawSource />
    </Status>
    <FriendsCount>2741</FriendsCount>
    <ProfileBackgroundColor>000000</ProfileBackgroundColor>
    <UtcOffset>3600</UtcOffset>
    <ProfileTextColor>000000</ProfileTextColor>
    <ProfileBackgroundImageUrl>http://abs.twimg.com/images/themes/theme1/bg.png</ProfileBackgroundImageUrl>
    <TimeZone>London</TimeZone>
    <FavouritesCount>221</FavouritesCount>
    <ListedCount>48</ListedCount>
    <ProfileLinkColor>CD0032</ProfileLinkColor>
    <StatusesCount>1270</StatusesCount>
    <ProfileSidebarFillColor>000000</ProfileSidebarFillColor>
    <ProfileSidebarBorderColor>000000</ProfileSidebarBorderColor>
    <IsProfileBackgroundTiled>false</IsProfileBackgroundTiled>
    <IsVerified>false</IsVerified>
    <IsGeoEnabled>false</IsGeoEnabled>
    <Language>en</Language>
    <CreatedDate>2012-05-14T16:11:39Z</CreatedDate>
    <FollowRequestSent>false</FollowRequestSent>
    <IsTranslator>false</IsTranslator>
    <ContributorsEnabled>false</ContributorsEnabled>
    <ProfileBackgroundImageUrlHttps>https://abs.twimg.com/images/themes/theme1/bg.png</ProfileBackgroundImageUrlHttps>
    <ProfileImageUrlHttps>https://pbs.twimg.com/profile_images/751384996125020160/C0SujFVc_normal.jpg</ProfileImageUrlHttps>
    <IsDefaultProfile>false</IsDefaultProfile>
  </Follower>
</Followers>
```