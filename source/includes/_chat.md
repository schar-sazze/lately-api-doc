# Chat

## Chat room 생성

특정 seller 와의 채팅방을 생성합니다.

```shell
curl -XPOST "lately.co.kr/chat-api/V1/rooms" \
  -H 'Authorization: Bearer meowmeowmeow' \
  -H "Content-Type: application/json" \
  -d '{
         "userId": "seller1"
      }'
```

> 위의 명령어는 [Room](#chat-room) 를 반환합니다

``` json
{
    "_id": "56ecb1403d37c3b2f1158703",
    "sellerId": "seller1",
    "userId": "participants12",
    "__v": 0,
    "createdTime": "2016-03-19T01:54:08.584Z"
}
```


### HTTP Request

`POST chat-api/rooms/`

### Response

JSON [Room](#chat-room)

### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
userId |  | 대화를 하고자 하는 seller 의 user id


## Message 전송

채팅방에 메세지를 전송합니다

```shell
curl -XPOST "lately.co.kr/chat-api/V1/rooms/56ecb0d90b19a68af166585a/messages" \
  -H 'Authorization: Bearer meowmeowmeow' \
  -H "Content-Type: application/json" \
  -d '{
         "message": "hello seller!"
     }'
```

> 위의 명령어는 [Message](#chat-message) 를 반환합니다

``` json
{
    "__v": 0,
    "message": "hello seller!",
    "roomId": "56ecb0d90b19a68af166585",
    "userId": "participants12",
    "_id": "56f09132dfbb293a0c1ffa0f",
    "createdTime": "2016-03-22T00:26:26.527Z"
}
```


### HTTP Request

`POST chat-api/rooms/:roomId/messages`

### Response

JSON [Message](#chat-message)

### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
message |  | 보내고자하는 메세지


## Getting Messages

채팅방의 메세지들을 가져옵니다

```shell
curl -XGET "lately.co.kr/chat-api/V1/rooms/56ecb0d90b19a68af166585a/messages?limit=2&before=2016-03-22T00:38:53.954Z" \
  -H 'Authorization: Bearer meowmeowmeow' \
  -H "Content-Type: application/json" \
  -d '{
         "limit": "hello seller!"
     }'
```

> 위의 명령어는 [Message](#chat-message)의 리스트를 반환합니다

``` json
[{
    "_id": "56f0941edfbb293a0c1ffa10",
    "message": "hello seller! 2",
    "roomId": "56ecb0d90b19a68af166585",
    "userId": "participants12",
    "__v": 0,
    "createdTime": "2016-03-22T00:38:54.954Z"
}, {
    "_id": "56f09132dfbb293a0c1ffa0f",
    "message": "hello seller!",
    "roomId": "56ecb0d90b19a68af166585",
    "userId": "participants12",
    "__v": 0,
    "createdTime": "2016-03-22T00:26:26.527Z"
}]
```


### HTTP Request

`POST chat-api/rooms/:roomId/messages`

### Response

JSON list of [Message](#chat-message)

### Query Parameters
Parameter | Default | Description
--------- | ------- | -----------
before | now | 이 시간 이전의 메세지들만 반환
limit | 10 | 가져오고자 하는 메세지의 개수
