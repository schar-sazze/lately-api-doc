---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='http://devdocs.magento.com/swagger/index.html'>Magento 공식 API 문서</a>
  - <a href='http://devdocs.magento.com/guides/v2.0/rest/list.html'>Magento 모듈별 REST API 목록</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>


includes:
  - cms
  - chat
  - wishlist
  - objects


search: true
---

# Introduction

[Lately](http://lately.co.kr)는 Magento 2.0 기반 서비스입니다. 공식 Magento API에서 다소
수정된 부분이 있을 수 있으며, 공식 API 이외의 추가된 API들을 제공합니다.

# Authentication

## Token 기반 인증

> 사용자 계정

``` shell
curl -X POST "lately.co.kr/rest/V1/integration/customer/token" \
     -H "Content-Type: application/json" \
     -d '{ "username": "customer@example.com", "password": "password" }'
```

> 관리자 계정

``` shell
curl -X POST "lately.co.kr/rest/V1/integration/admin/token" \
     -H "Content-Type: application/json" \
     -d '{ "username": "customer@example.com", "password": "password" }'
```

> 결과는 다음과 같습니다.

``` txt
gopu2mmnh119bgdwp57d6tdbow5atyxc
```

Lately API에서 특정 API들은 서버에 요청을 할 때 사용자 혹은 관리자 계정의 권한을 필요로 합니다. 해당
API들에 권한이 명시되어있지 않으면 권한없이 요청할 수 있는 API입니다. 다음 API들에서 사용자 혹은
관리자의 계정을 통해 인증이 필요한 API에서 사용될 token을 가져올 수 있습니다.

### HTTP Request

- `POST V1/integration/customer/token`
- `POST V1/integration/admin/token`

### Payload

Name | Type | Description
-----|------|------------
username | string | 사용자 혹은 관리자의 계정
password | string | 계정의 패스워드

### Returns

32자리의 16진수 문자들로 구성된 token을 리턴합니다.

## Token을 통한 요청

> token을 포함한 요청

```shell
curl "api_endpoint_here"
  -H "Authorization: Bearer meowmeowmeow"
```

> `meowmeowmeow` 부분을 API token으로 수정했는지 확인하세요.

Lately API에서 특정 API들은 서버에 요청을 할 때 사용자 혹은 관리자 계정의 API token이 다음과 같이
헤더에 포함되어있어야 합니다.

`Authorization: Bearer meowmeowmeow`

<aside class="notice">
<code>meowmeowmeow</code>를 사용자 혹은 관리자 계정의 API token으로 교체해야합니다.
</aside>
