# GitHub Popular Searches
### A collection to discover popular repositories on [GitHub](https://github.com) for a given search query.

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/e6d6eaba6eeaaec69bc5)

> Set the following environment variables before you run this collection : 
- **{{searchTerm}}** : the query you want to search
- **{{maxSize}}** : maximum number of repositories you want to fetch

It sends the popular repository on Slack channel using webhook.

> This collection uses [Github API](https://developer.github.com/v3/) to fetch comments and sends a report to an internal Slack channel using a [webhook](https://api.slack.com/incoming-webhooks#sending_messages).

## API Calls made

1. **[GET]() npm search** - API call to [NPM](https://www.npmjs.com) to fetch the popular GitHub Repositories for a given search query.

```
http://registry.npmjs.com/-/v1/search?text={{searchTerm}}&size={{maxSize}}
```

2. **[GET]() fetch comments** - Fetching *comments* for each repositories using [GitHub API](https://api.github.com/).
```
https://api.github.com/repos/{{userName}}/{{repoName}}/comments  
```
- **{{repoName}}** : Name of the GitHub repository
- **{{userName}}** : GitHub username for the given repository

3. **[POST]() calculate sentiments** - Calculating sentiment using [ParallelDots API](https://www.paralleldots.com) for the comments of given GitHub repository.

```
https://apis.paralleldots.com/v3/sentiment?text={{sentimentText}}&api_key={{apiKey}}
```

4. **[POST]() push to slack** - Pushing most popular repos to Slack using [webhook](https://api.slack.com/incoming-webhooks).

```
https://hooks.slack.com/services/XXXXXXXXX
```
[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/e6d6eaba6eeaaec69bc5)
