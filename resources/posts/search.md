# Post Search

Endpoints:

* [Search posts](#get-posts-search)


## <span class="method method-get">GET</span> /posts/search {#get-posts-search .endpoint}

Scope: <span class="endpoint-meta">none</span>

Retrieve a list of posts filtered by the given criteria.

### Query Parameters

#### Search

Name|Description
-|-
`q`|List of words included in posts

#### Sort

Name|Description
-|-
`order`|One of id or relevance. Default is by relevance

#### Filter

Name|Description
-|-
`tags`|Comma-separated list of tags. Any matches returned. Do not include `#`
`has_mentions`|Whether to include posts with any mentions. Excludes other mentions filters below
`mentions`|Comma-separated list of mentions. Any matches returned. Do not include `@`
`leading_mentions`|Comma-separated list of mentions at the beginning of a post. Any matches returned. Do not include `@`
`links`|Comma-separated list of URLs. Any matches returned
`link_domains`|Comma-separated list of domains. Any matches returned. Do not include `http://` or `www` in front of domain
`is_directed`|If true, only include directed posts
`is_revised`|If true, only include revised posts
`is_nsfw`|If false, does not include NSFW posts
`is_reply`|If true, only include replies
`client_id`|Only include posts created by this client ID
`creator_id`|Only include posts created by this user ID
`reply_to`|Only include posts replying to this post
`thread_id`|Only include posts in this thread
`user_types`|Comma-separated list of user types of: human, feed, bot
`raw_types`|Comma-separated list of attached raw types. Any matches returned

##### Example {.example-code}

```bash
curl "https://api.pnut.io/v0/posts/search?tags=mndp,MondayNightDanceParty" \
    -H "Authorization: Bearer ${ACCESS_TOKEN}" \
    -H "X-Pretty-Json: 1"
```

Returns a list of posts

```json
{
    "meta": {
        "more": true,
        "max_id": "0",
        "min_id": "0",
        "code": 200
    },
    "data": [
        {"...Post Object..."},
        {"...Post Object..."}
    ]
}
```