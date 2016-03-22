# Objects

API 에서 사용되는 객체들의 형식을 설명합니다.

## Chat Room

각 채팅방을 나타내는 객체

Name | Type | Description
---- | ---- | -----------
_id | string | ID of this chat room
userId | string | User ID
sellerId | string | seller user ID
createdTime | string | time of chat room created ISO 8601 date (2015-03-25T12:00:00)

## Chat Message

채팅 메세지

Name | Type | Description
---- | ---- | -----------
_id | string | ID of this message
userId | string | Sender User ID
message | string | message
createdTime | string | time of message sent ISO 8601 date (2015-03-25T12:00:00)