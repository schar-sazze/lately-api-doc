# Basic Rule

## 검색 및 필터 (searchCriteria)

```shell
curl "dev.lately.co.kr/rest/V1/products?searchCriteria\[pageSize\]=10&searchCriteria\[currentPage\]=0" \
-H "Content-Type: application/json" 
# 혹은
curl "http://dev.lately.co.kr/rest/V1/products\
?searchCriteria\[filterGroups\]\[0\]\[filters\]\[0\]\[field\]=sku\
&searchCriteria\[filterGroups\]\[0\]\[filters\]\[0\]\[value\]=11\
&searchCriteria\[filterGroups\]\[0\]\[filters\]\[0\]\[condition_type\]=in" 

```

> 위의 명령어는 다음과 같은 구조의 JSON을 리턴합니다

``` json
{
  "items": [...],
  "search_criteria": {
    "filter_groups": [],
    "page_size": 10,
    "current_page": 0
  },
  "total_count": 6
}
```

