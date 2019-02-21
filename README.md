# GitHub Popular Searches

[![Made by Vinit Shahdeo](https://forthebadge.com/images/badges/built-with-love.svg)](https://documenter.getpostman.com/view/6186519/RznEKdvc) [![Powered By](https://forthebadge.com/images/badges/powered-by-oxygen.svg)](https://github.com/vinitshahdeo)

### A [Postman](https://www.getpostman.com/) collection to discover popular repositories on [GitHub](https://github.com) for a given search query.

```js

  _____   ____   _____ _______ __  __          _   _ 
 |  __ \ / __ \ / ____|__   __|  \/  |   /\   | \ | |
 | |__) | |  | | (___    | |  | \  / |  /  \  |  \| |
 |  ___/| |  | |\___ \   | |  | |\/| | / /\ \ | . ` |
 | |    | |__| |____) |  | |  | |  | |/ ____ \| |\  |
 |_|     \____/|_____/   |_|  |_|  |_/_/    \_\_| \_|
                                                     
                                                     
```

> **This collection is published [here](https://documenter.getpostman.com/view/6186519/RznEKdvc).**

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/e6d6eaba6eeaaec69bc5)

> Set the following environment variables before you run this collection : 
- ` {{searchTerm}} ` : the query you want to search
- ` {{maxSize}} ` : maximum number of repositories you want to fetch

It sends the popular repository on Slack channel using webhook.

> This collection uses [Github API](https://developer.github.com/v3/) to fetch comments and sends a report to an internal Slack channel using a [webhook](https://api.slack.com/incoming-webhooks#sending_messages).

## API Calls made

1. **[GET]() npm search** - API call to [NPM](https://www.npmjs.com) to fetch the popular GitHub Repositories for a given search query.

```js
http://registry.npmjs.com/-/v1/search?text={{searchTerm}}&size={{maxSize}}
```

2. **[GET]() fetch comments** - Fetching *comments* for each repositories using [GitHub API](https://api.github.com/).

```js
https://api.github.com/repos/{{userName}}/{{repoName}}/comments  
```

 - ` {{repoName}} ` : Name of the GitHub repository
 - ` {{userName}} ` : GitHub username for the given repository

3. **[POST]() calculate sentiments** - Calculating sentiment using [ParallelDots API](https://www.paralleldots.com) for the comments of given GitHub repository.

```js
https://apis.paralleldots.com/v3/sentiment?text={{sentimentText}}&api_key={{apiKey}}
```

4. **[POST]() push to slack** - Pushing most popular repos to Slack using [webhook](https://api.slack.com/incoming-webhooks).

```js
https://hooks.slack.com/services/XXXXXXXXX
```

## Thanks!
[![Thanks](https://forthebadge.com/images/badges/you-didnt-ask-for-this.svg)](https://facebook.com/vinit.shahdeo)

Glad to see you here! I'm social. Let's `get connected`.

<a href="https://www.facebook.com/vinit.shahdeo/" target="_blank"><img height="32" width="32" src="https://cdn.jsdelivr.net/npm/simple-icons@latest/icons/facebook.svg" /></a> &nbsp;&nbsp;<a href="https://twitter.com/Vinit_Shahdeo" target="_blank"><img height="32" width="32" src="https://cdn.jsdelivr.net/npm/simple-icons@latest/icons/twitter.svg" /></a> &nbsp;&nbsp;<a href="https://www.linkedin.com/in/vinitshahdeo/" target="_blank"><img height="32" width="32" src="https://cdn.jsdelivr.net/npm/simple-icons@latest/icons/linkedin.svg" /></a>
