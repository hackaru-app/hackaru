![Header](./docs/images/header.png)

## What?
Hackaru (測る) is Simple Timetracking App.  
> "測る" means "Measure" in Japanese.

### Features

- PWA support. It can use on iOS and Android.
- OAuth2 authentication support.
- Webhook Support (e.g., Timer started, Timer stopped)
- Completely open source. You can build on your server.

## Usage

1. Install [Docker](https://docs.docker.com/install/) and [Docker Compose](https://docs.docker.com/compose/install/).

2. Clone this repository.
```
$ git clone https://github.com/ktmouk/hackaru.git
$ cd /hackaru
```

3. Copy and rename sample ENV files.
```
$ cp .env.api.sample .env.api
$ cp .env.web.sample .env.web
```

4. Set `SECRET_KEY_BASE` and `JWT_SECRET` params in `.env.api` file.  
You can use `rake:secret` command to generate secrets.  
```
$ docker-compose run --rm api rails db:create db:migrate
b75ed1d79e4db7aefa5f... # Copy this secret to clipboard.
```
We strongly recommend to `JWT_SECRET` set different value from `SECRET_KEY_BASE.`  
```
# Rails
RAILS_ENV=production
RAILS_LOG_TO_STDOUT=true
SECRET_KEY_BASE=    # Set secret.
JWT_SECRET=         # Set secret.
...
```
5. Run DockerCompose.
```
$ docker-compose up
```
6. Finally, Create and migrate a database.
```
$ docker-compose run --rm api rails db:create db:migrate
```
7. You can access Hackaru from http://localhost:3000.

## How is it working?
![Architecture](./docs/images/architecture.svg)

- API container serve RESTful API and OAuth2 authentication.
- Web container send HTML/CSS/JS to browser. and fetch JSON from API server on a background.

### Repositories
- API - [ktmouk/hackaru-web](https://github.com/ktmouk/hackaru-web)
- WebUI - [ktmouk/hackaru-api](https://github.com/ktmouk/hackaru-api)

## Fix, Feedback
- If you found bad English :memo:, or have a new idea :bulb:, Please send PullRequest! :relaxed:

## License
- [MIT](./LICENSE)
