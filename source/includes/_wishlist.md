# Wishlist

## Get Wishlist

```shell
curl "lately.co.kr/rest/V1/wishlist/mine" \
  -H 'Authorization: Bearer meowmeowmeow'
```

> 위의 명령어는 다음과 같은 구조의 JSON을 리턴합니다

``` json
{
  "wishlist_id": 2,
  "customer_id": 3,
  "shared": false,
  "sharing_code": "8baa5a177e0716b2b4e08de0b813f45f",
  "updated_at": "2016-03-08 11:23:35",
  "items": [
    {
      "wishlist_item_id": 1,
      "wishlist_id": 2,
      "product_id": 1,
      "store_id": 1,
      "added_at": "2016-03-25 12:30:19",
      "qty": 1
    },
    ...
  ]
}
```

현재 사용자의 찜(wishlist) 목록을 반환합니다.

### HTTP Request

`GET rest/V1/wishlist/mine`

### Response

JSON [Wishlist](#wishlist-object)



## Add an Item to Wishlist

```shell
curl -X POST "lately.co.kr/rest/V1/wishlist/mine/2" \
  -H 'Authorization: Bearer meowmeowmeow'
```

> 위의 명령어는 다음과 같은 구조의 JSON을 리턴합니다

``` json
{
  "wishlist_item_id": 2,
  "wishlist_id": 2,
  "product_id": 2,
  "store_id": 1,
  "added_at": "2016-03-25 12:30:26",
  "qty": 1
}
```

현재 사용자의 찜 목록에 제품을 추가합니다.

### HTTP Request

`POST rest/V1/wishlist/mine/:product_id`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
product_id |  | 추가할 제품의 ID

### Response

JSON [Wishlist Item](#wishlist-item)



## Delete an Item in Wishlist

```shell
curl -X DELETE "lately.co.kr/rest/V1/wishlist/mine/2" \
  -H 'Authorization: Bearer meowmeowmeow'
```

> 위의 명령어는 리턴하는 값이 없습니다.


현재 사용자의 찜 목록에 제품을 삭제합니다.

### HTTP Request

`DELETE rest/V1/wishlist/mine/:product_id`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
product_id |  | 삭제할 제품의 ID



## How Many Wished

```shell
curl "lately.co.kr/rest/V1/wishlist/1"\
  -H "Content-Type: application/json"
```

> 위의 명령어는 다음과 같은 구조의 JSON을 리턴합니다

``` json
{
  count: 2
}
```

해당 제품을 찜 목록에 추가한 사용자의 숫자를 반환합니다.

### HTTP Request

`GET rest/V1/wishlist/:product_id`


### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
product_id |  | 조회할 제품의 ID

### Response

Name | Type | Description
---- | ---- | -----------
count  | int | 찜 목록에 추가한 사용자 수

