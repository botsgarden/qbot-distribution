# qbot-distribution
QBot is a cloud native bot, written in java, scalable and expandable with microservices

QBot chats with:

- GitHub issues
- GitBucket issues (experimental)
- Slack
- soon: RocketChat, GitLab, ...

## Setup QBot

### Requirements

- Redis database: microservices discovery backend
- DVCS:
  - GitHub account + 2nd GitHub account for the bot
  - (Experimental) or GitBucket account + 2nd GitBucket account for the bot

### Set environment variables

```shell
# DVCS PART
BOT_HANDLE=indythebot # the GitHub handle of your bot
BOT_TOKEN=<the web token of your bot> # you need to create a GitHub user
DVCS_HOST=https://api.github.com # the url of the DVCS api, here, it's for GitHub.com

# RUN PART
JAVA_VERSION=8
PORT=8080 # only if you want to change the port (default is 9090)

# SLACK PART: WIP
# ROCKETCHAT PART: WIP 

# REDIS PART
REDIS_HOST=<...> # default is "127.0.0.1"
REDIS_PASSWORD=<...> # default is null
REDIS_PORT=<...> # default is 6379
REDIS_URL=<...> # optional, needed for some cloud providers 
```

:warning: If you run your bot inside a VM or a container, the "external" port to reach the bot coul be different than `PORT`

### Hooks

#### GitHub

You have to create a webhook in the settings tab of you repository
- with this url `http://<your-bots-domain>/hub/hey/<bots-handle>`
- chose the response format (`Content type`): `application/json` 
- secret: `not implemented` | 🚧 *WIP*
- select individual events: issues and issue comment

#### GitBucket

- Same procedure as GitHub

#### GitLab

> WIP

#### Slack

> WIP

#### RocketChat

> WIP

## Deployment

> WIP



