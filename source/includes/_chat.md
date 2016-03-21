# Chat

## Chat room 생

```shell
curl -XPOST "lately.co.kr/chat-api/rooms \
  -H 'Authorization: Bearer meowmeowmeow'
  -d '{
         "userId": "seller1"
     }'
```

> 위의 명령어는 [Room](#Object-)

``` json
{
  "items": [
    {
      "identifier": "no-route",
      "title": "404 Not Found",
      "page_layout": "2columns-right",
      "meta_keywords": "Page keywords",
      "meta_description": "Page description",
      "content_heading": "Whoops, our bad...",
      "content": "<dl>\r\n<dt>The page you requested was not found, and we have a fine guess why.</dt>",
      "creation_time": "2016-03-01 19:43:56",
      "update_time": "2016-03-01 19:43:56",
      "sort_order": "0",
      "active": true
    },
    {
      "identifier": "home",
      "title": "Home Page",
      "page_layout": "1column",
      "content_heading": "Home Page",
      "creation_time": "2016-03-01 19:43:56",
      "update_time": "2016-03-07 08:05:20",
      "sort_order": "0",
      "active": true
    },
    ...
 ],
  "search_criteria": {
    "filter_groups": [],
    "page_size": 10,
    "current_page": 0
  },
  "total_count": 6
}
```

특정 기준에 해당하는 페이지들을 리턴합니다.

### HTTP Request

`GET cms/page/search`

## Get a Specific CMS Page

```shell
curl "http://staging.lately.co.kr/rest/V1/cms/page/2"
```

> The above command returns JSON structured like this:

``` json
{
  "id": 2,
  "identifier": "home",
  "title": "Home Page",
  "page_layout": "1column",
  "content_heading": "Home Page",
  "creation_time": "2016-03-01 19:43:56",
  "update_time": "2016-03-07 08:05:20",
  "sort_order": "0",
  "active": true
}
```

This endpoint retrieves a specific page

### HTTP Request

`GET cms/page/:page_id`

## Get All CMS blocks

```shell
curl "http://staging.lately.co.kr/rest/V1/cms/block/search?searchCriteria\[pageSize\]=10&searchCriteria\[currentPage\]=0"
# or
curl -G "http://staging.lately.co.kr/rest/V1/cms/block/search" \
     -d "searchCriteria[pageSize]=10" \
     -d "searchCriteria[currentPage]=0"
```

> The above command returns JSON structured like this:

``` json
{
  "items": [
    {
      "identifier": "footer_links_block",
      "title": "Footer Links Block",
      "content": "<ul class=\"footer links\">\n    <li class=\"nav item\"><a href=\"{{store url=\"about-us\"}}\">About us</a></li>\n    <li class=\"nav item\"><a href=\"{{store url=\"customer-service\"}}\">Customer Service</a></li>\n</ul>\n",
      "creation_time": "2016-03-07 08:05:20",
      "update_time": "2016-03-07 08:05:20",
      "active": true
    },
    {
      "identifier": "contact-us-info",
      "title": "Contact us info",
      "content": "<div class=\"contact-info cms-content\">\n   <p class=\"cms-content-important\">We love hearing from you, our Luma customers. Please contact us about anything at all. Your latest passion, unique health experience or request for a specific product. We’ll do everything we can to make your Luma experience unforgettable every time. Reach us however you like</p>\n   <div class=\"block block-contact-info\">\n       <div class=\"block-title\">\n           <strong>Contact Us Info</strong>\n       </div>\n       <div class=\"block-content\">\n           <div class=\"box box-phone\">\n               <strong class=\"box-title\">\n                   <span>Phone</span>\n               </strong>\n               <div class=\"box-content\">\n                   <span class=\"contact-info-number\">1-800-403-8838</span>\n                   <p>Call the Luma Helpline for concerns, product questions, or anything else. We’re here for you 24 hours a day - 365 days a year.</p>\n               </div>\n           </div>\n           <div class=\"box box-design-inquiries\">\n               <strong class=\"box-title\">\n                   <span>Apparel Design Inquiries</span>\n               </strong>\n               <div class=\"box-content\">\n                   <p>Are you an independent clothing designer? Feature your products on the Luma website! Please direct all inquiries via email to: <a href=\"mailto:cs@luma.com\">cs@luma.com</a></p>\n               </div>\n           </div>\n           <div class=\"box box-press-inquiries\">\n               <strong class=\"box-title\">\n                   <span>Press Inquiries</span>\n               </strong>\n               <div class=\"box-content\">\n                   <p>Please direct all media inquiries via email to: <a href=\"mailto:pr@luma.com\">pr@luma.com</a></p>\n               </div>\n           </div>\n       </div>\n   </div>\n</div>\n",
      "creation_time": "2016-03-07 08:05:20",
      "update_time": "2016-03-07 08:05:20",
      "active": true
    },
    ...
  ],
  "search_criteria": {
    "filter_groups": [],
    "page_size": 10,
    "current_page": 0
  },
  "total_count": 18
}
```


This endpoint retrieves blocks matching the specified criteria

### HTTP Request

`GET cms/block/search`

## Get a Specific CMS Block

```shell
curl "http://staging.lately.co.kr/rest/V1/cms/block/1"
```

> The above command returns JSON structured like this:

``` json
{
  "id": 1,
  "identifier": "footer_links_block",
  "title": "Footer Links Block",
  "content": "<ul class=\"footer links\">\n    <li class=\"nav item\"><a href=\"{{store url=\"about-us\"}}\">About us</a></li>\n    <li class=\"nav item\"><a href=\"{{store url=\"customer-service\"}}\">Customer Service</a></li>\n</ul>\n",
  "creation_time": "2016-03-07 08:05:20",
  "update_time": "2016-03-07 08:05:20",
  "active": true
}
```

This endpoint retrieves a specific page

### HTTP Request

`GET cms/block/:block_id`
