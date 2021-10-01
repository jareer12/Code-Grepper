# Code Grepper APIs

Any material used on this Github repository is the property of [Taylor Hawkes(Code Grepper)](https://www.codegrepper.com/) Document written by [Jareer](https://www.codegrepper.com/profile/jareer). Don't forget to Star the repo and visit frequently for new updates. List of Code Grepper APIs. Below is a table that shows what type of request does the API receive.

| Symbol | Type |
|---|---|
| 🟢 |  **`GET`** |
| 🔵 |  **`PUT`** |
| 🔴 |  **`POST`** |
| ⚪ |  **`DELETE`** |
| ⚫ |  **`OPTIONS`** |

## [Application Pages][MainPage]

Shows answers requires the `q` parameter.

```yaml
https://www.codegrepper.com/search.php 🟢
```

View a user's profile with their username(real_name)

```yaml
https://www.codegrepper.com/profile/jareer 🟢
```

View a user's profile with their userId. This API requires `id` parameter.

```yaml
https://www.codegrepper.com/app/profile.php 🟢
```

## [Answers][MainPage]

saves an answer to the codegrepper website,

```yaml
https://www.codegrepper.com/api/save_answer.php 🔴
```

Publish/save an answer.

```yaml
https://www.codegrepper.com/api/save_comment.php 🔴
```

Updates the answer.

```yaml
https://www.codegrepper.com/api/update_answer.php 🔴

```

Shows what answers are needed.

```yaml
https://www.codegrepper.com/api/get_terms_needing_answers.php 🟢
```

Retrieves the comment(s) of an answer.

```yaml
https://www.codegrepper.com/api/get_answers_comments.php?aid=287391&u=98467 🟢
```

Returns answers for a specific search(v2). Uses the `v`, `s` & `u` parameters(`?v=2&s=grepper&u=98467`).

```yaml
https://www.codegrepper.com/api/get_answers_1.php
```

Returns answers for a specific search. Uses the `q` & `search_options` parameters(`?q=grepper&search_options=search_titles`).

```yaml
https://www.codegrepper.com/api/search.php 🟢
```

## [Users][MainPage]

Shows how many people did the user helped & and the ammount of problems solved.

```yaml
https://www.codegrepper.com/api/profile_helped_stats.php?id=98467
```

Returns JSON data for a user's profile. Like `profile_image`, `fun_name`, `real_name`, `donate_link` etc.

```yaml
https://www.codegrepper.com/api/profile.php?id=98467 🟢
```

**Example:**

```yaml
{
  "profile_image": "98467_hKuVkwhdUxieQAfc5lVurPuwSPTQFiVSnWEIS8l4gecLZdSa0g3vba4.gif",
  "fun_name": "Undefined",
  "real_name": "Jareer",
  "twitter_name": "",
  "donate_link": "https://jareer.xyz/donate",
  "how_to_help": "My Grepper Experience has been really POG, looking forward to collaborate. Rigby#6654(discord)",
  "location": "Mars",
  "is_rank_private": 0,
  "is_activity_private": 1,
  "is_expertise_private": 0,
  "is_daily_activity_private": 1,
  "enable_coding_activity": 1
}
```

This API shows what Programming language(s) does the user use, returns an array in JSON. The Data includes `SucessCode`, `Name` etc.

```yaml
https://www.codegrepper.com/api/get_user_code_languages.php 🟢
```

```yaml
{
    "success": true,
    "ucl": [
        {
            "lkey": "String",
            "name": "String",
            "enabled": 0
        }
    ]
}
```

Returns user's belt stats, this data includes Previous Belt, Next Belt & current belt percentage.

```yaml
https://www.codegrepper.com/api/get_user_stats.php?uid=98467 🟢
```

```yaml
{
    "coding_belt": [
        "String",
        0.000,
        "String"
    ],
    "is_rank_private": "0",
    "success": true
}
```

Shows user's feed, requires auth

```yaml
https://www.codegrepper.com/api/get_my_feed.php
```

**Example:**

```yaml
{
  "activity": [
    {
      "feed_type": "recent_answer",
      "answer_created_at": "2021-10-01 04:52:16",
      "answer": "int a = 80;\nint b = 20;\nint addition(int number1, int number2)\n{\n\tint result = number1 + number2;\n\treturn result;\n}\nConsole.WriteLine(addition( a,  b));",
      "user_id": "262702",
      "id": 333666,
      "answer_title": "function in c# to do addition",
      "fun_name": "Empire of programmers ",
      "profile_slug": "vishnu",
      "profile_image": "262702_IeIHn2AeTy0QlU1cf7V8LWlIMouvwH0PjZA4UVKk5gw8mw952eozbZN.gif",
      "answer_user_id": 262702
    }
  ]
}
```

Shows all the users on the community page, requires auth. This data includes `UserId`, `Username`, `BeltScore`, `BeltRank` etc.

```yaml
https://www.codegrepper.com/api/get_belt_users.php?offset=0&limit=500 🟢
```

**Example:**

```yaml
{
    "users": [
        {
            "user_id": 0,
            "fun_name": "String",
            "is_rank_private": 0,
            "belt_score": 0,
            "profile_slug": "String",
            "profile_image": "String",
            "belt_rank": "String"
        }
    ]
}
```

This API is used to follow a user, you must be authenticated to do this. This API returns either `1` or `0`.

```yaml
https://www.codegrepper.com/api/follow.php?follow_user_id=98467&follow=1 🟢
```

```yaml
1
```

## [Teams][MainPage]

This API is used to join a team.

```yaml
https://www.codegrepper.com/api/join_team.php 🔴
```

```yaml
{
    team_member_id: 0000
}
```

This API adds users to your team.

```yaml
https://www.codegrepper.com/api/add_team_members.php 🔴
```

An auto completor for the team search users. This API can be used to get user's ID by their username.

```yaml
https://www.codegrepper.com/api/autocomplete_users_search.php?team_id=1&q=Jareer 🟢
```

**Example:**

````yaml
[
  {
    "is_team_member": null,
    "fun_name": "Undefined",
    "id": 98467,
    "real_name": "Jareer",
    "profile_image": "98467_hKuVkwhdUxieQAfc5lVurPuwSPTQFiVSnWEIS8l4gecLZdSa0g3vba4.gif"
  },
]
````

Shows all the Team answers, you need to be authenticated & in the team to retreive proper data.

```yaml
https://www.codegrepper.com/api/get_team_answers.php?&offset=0&sort_by=id_desc&team_id=348 🟢
```

```yaml
{
    "answers": [
        {
            "answer_user_id": "String",
            "is_others_answer": 0,
            "search_answer_user_id": 0,
            "fun_name": "String",
            "i_upvoted": "String",
            "upvotes": "String",
            "downvotes": "String",
            "score": "String",
            "total_answer_hits": 19,
            "term": "Question",
            "created_at": "String",
            "bounty": null,
            "answer": "String",
            "language": "String",
            "bounty_approved": null,
            "id": 0
        }
    ],
    "total_count": 88
}
```

## [Settings][MainPage]

The update privacy API is used to update your privacy settings, you can either set it to `true` or `false`, 0 means false 1 means true.

```yaml
https://www.codegrepper.com/api/update_extension_privacy.php 🔴
```

Updates your **[My programming language][Settings]** settings.

```yaml
https://www.codegrepper.com/api/update_my_code_languages.php?l=whatever&enabled=1 🟢
```

## [Other][MainPage]

API used while logging in.

```yaml
https://www.codegrepper.com/api/login.php 🔴
```

```yaml
{
    "chrome_grepper_id": "",
    "user_id": "",
    "email": "Jareer@gmail.com",
    "password": "adwsawdsa",
}
```

API to register users.

```yaml
https://www.codegrepper.com/api/register.php 🔴
```

```yaml
{
    "chrome_grepper_id": "",
    "user_id": "",
    "email": "Jareer@gmail.com",
    "password": "adwsawdsa",
}
```

API used to log users out

```yaml
https://www.codegrepper.com/api/logout.php 🟢
```

The reset password API.

```yaml
https://www.codegrepper.com/api/reset_password.php 🔴
```

```yaml
{
    "chrome_grepper_id": "",
    "user_id": "",
    "email": "Jareer@gmail.com",
}
```

The feedback api, used to send feedback to the Code grepper devs.

```yaml
https://www.codegrepper.com/api/send_feedback.php 🔴
```

Get who to follow, something that the algorithm mines from the database. Basically follow recommendation.

```yaml
https://www.codegrepper.com/api/get_who_to_follow.php 🟢
```

An Auto-completor for the [**Search**](https://www.codegrepper.com/search.php) page.

```yaml
https://www.codegrepper.com/api/search_autocomplete.php?q=js 🟢
```

Just a random route used as a CDN returns Images, these images are used in the meta tags of the search page.

```yaml
https://www.codegrepper.com/codeimages/for-loop-javascript.png 🟢
```

This API shows all the users answer stats.

```yaml
https://www.codegrepper.com/api/get_user_answer_stats.php?statstype=views&answer_id=null&daterange=null 🟢
```

```yaml
{
  "views": [
    {
      "created_at": "2020-10-15",
      "views": 0,
      "copies": 0,
      "upvotes": 0
    }
  ]
}
```

## Dealing with Authorization(s)

Every usser on Code Grepper has a unique `PHPSSESID` which is used to authenticate users. Follow the steps below To retrieve this token.

### Usage

Use this in `POST` requests headers `cookie: PHPSESSID=`.

### Find PHPSESSID

* Add the [EditThisCookie](https://chrome.google.com/webstore/detail/editthiscookie/fngmhnnpilhplaeedifhccceomclgfbg?hl=en) chrome extension.
* Open any page on Codegrepper.com
* Open EditThisCookie and click on `PHPSESSID`
* Copy and use it ;)

[MainPage]: https://dahood.xyz/
[TaylorProfile]: https://github.com/TaylorHawkes
[Profile]: https://www.codegrepper.com/app/profile.php?id=98467
[Settings]: https://www.codegrepper.com/app/settings-code-languages.php
