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

## Wishlist Object

찜 목록

Name | Type | Description
---- | ---- | -----------
wishlist_id  | int    | Wishlist ID
customer_id  | int    | Customer ID
shared       | int    | Sharing flag (0 or 1)
sharing_code | string | Sharing encrypted code
updated_at   | string | Last updated date
items | array([Wishlist Item](#wishlist-item)) | Wishlist items

## Wishlist Item

찜 항목

Name | Type | Description
---- | ---- | -----------
wishlist_item_id  | int    | Wishlist item ID
wishlist_id       | int    | Wishlist ID
product_id        | int    | Product ID
store_id          | int    | Store ID
added_at          | string | Add date and time
description       | string | Short description of wish list item
qty               | int    | Qty
