---
slug: downloading-following-from-twitter
redirect_from: "/article/889-download-following"
title: Downloading Following from Twitter
---
This task will download all the Twitter accounts that your authenticated user follows.

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
<Followings>
  <Following>
    <Relationship>
      <Source>
        <Id>17710803</Id>
        <ScreenName>zynk</ScreenName>
        <Following>true</Following>
        <FollowedBy>false</FollowedBy>
        <NotificationsEnabled>false</NotificationsEnabled>
        <CanDirectMessage>false</CanDirectMessage>
        <IsBlocking>false</IsBlocking>
        <RawSource />
      </Source>
      <Target>
        <Id>148694817</Id>
        <ScreenName>test</ScreenName>
        <Following>false</Following>
        <FollowedBy>true</FollowedBy>
        <NotificationsEnabled />
        <CanDirectMessage />
        <IsBlocking />
        <RawSource />
      </Target>
      <RawSource />
    </Relationship>
    <RawSource>{"relationship":{"source":{"id":17710803,"id_str":"17710803","screen_name":"zynk","following":true,"followed_by":false,"live_following":false,"following_received":false,"following_requested":false,"notifications_enabled":false,"can_dm":false,"blocking":false,"blocked_by":false,"muting":false,"want_retweets":true,"all_replies":false,"marked_spam":false},"target":{"id":148694817,"id_str":"148694817","screen_name":"realisable","following":false,"followed_by":true,"following_received":false,"following_requested":false}}}</RawSource>
  </Following>
</Followings>
```