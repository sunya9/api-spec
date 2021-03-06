# Report

These are the current reasons that will be honored for reporting:

* `account_type`: posting in a behavior counter to the purposes of [account types](https://pnut.io/docs/resources/account-types)
* `nsfw`: unflagged mature material according to [the community guidelines](https://pnut.io/docs/resources/mature-content)
* `soliciting`: unwelcome soliciting
* `user_abuse`: use of the API or network to abuse another user

Endpoints:

* [Report a post](#post-posts-id-report)


## <span class="method method-post">POST</span> /posts/<span class="call-param">{post_id}</span>/report {#post-posts-id-report .endpoint}

Token: <span class="endpoint-meta">user</span>

Scope: <span class="endpoint-meta">any</span>

Report a post for abuse.

To test this endpoint, report a post by user [@testuser](/docs/dev_resources/testuser).

### URL Parameters

Name|Description
-|-
`post_id`|ID of the post to report.

### POST Body Data

Name|Description
-|-
`reason`|One of: `account_type`, `nsfw`, `soliciting`, `user_abuse`.

##### Example {.example-code}

```bash
curl "https://api.pnut.io/v0/posts/381576/report" \
    -H "Authorization: Bearer ${ACCESS_TOKEN}" \
    -H "X-Pretty-Json: 1"
```

Returns a 201

```json

```