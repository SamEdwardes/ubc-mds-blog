---
layout: post
title: How to safely store API keys
---

Many data science projects require us to use APIs to access data from websites. For example, [twitter.com](https://twitter.com) has an API you can use to access twitter data. You can apply for an API using [this link](https://developer.twitter.com/en/docs/ads/general/overview/adsapi-application).

Once you have been granted access to the API, special security keys will be generated. These keys are unique to you, and should never be shared with anyone. This poses an interesting challenge:

> How can we make our project open source without leaking sensitive information?

The key is to not hard code your keys into any of your applications. But we also do not want to have to type them in each time. To work around this, I suggest the following steps:

- You can create a JSON file that will look something like this:

```json
{
    "CONSUMER_KEY": "your-key-here1",
    "CONSUMER_SECRET": "your-key-here2",
    "ACCESS_TOKEN": "your-key-here3",
    "ACCESS_SECRET": "your-key-here4"
}
```

- Add the json file your `.gitignore`.
- when ever your code needs to reference the keys, read in the json file from your local computer.

Following the above steps should help keep your API keys safe!