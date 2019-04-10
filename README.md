# Hackaru

![Header](./docs/images/header.png)

## What?
Hackaru (測る) is Simple Timetracking App.  
> "測る" means "Measure" in Japanese.

## Features

- PWA support. It can use on iOS and Android.
- OAuth2 authentication support.
- Webhook Support (e.g., Timer started, Timer stopped)
- Completely open source. You can build on your server.

## Official website
You can use Hackaru on the official website. It's free.
- https://www.hackaru.app

> <style>.bmc-button img{width: 27px !important;margin-bottom: 1px !important;box-shadow: none !important;border: none !important;vertical-align: middle !important;}.bmc-button{line-height: 36px !important;height:37px !important;text-decoration: none !important;display:inline-flex !important;color:#ffffff !important;background-color:#FF813F !important;border-radius: 3px !important;border: 1px solid transparent !important;padding: 1px 9px !important;font-size: 22px !important;letter-spacing: 0.6px !important;box-shadow: 0px 1px 2px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 1px 2px 2px rgba(190, 190, 190, 0.5) !important;margin: 0 auto !important;font-family:'Cookie', cursive !important;-webkit-box-sizing: border-box !important;box-sizing: border-box !important;-o-transition: 0.3s all linear !important;-webkit-transition: 0.3s all linear !important;-moz-transition: 0.3s all linear !important;-ms-transition: 0.3s all linear !important;transition: 0.3s all linear !important;}.bmc-button:hover, .bmc-button:active, .bmc-button:focus {-webkit-box-shadow: 0px 1px 2px 2px rgba(190, 190, 190, 0.5) !important;text-decoration: none !important;box-shadow: 0px 1px 2px 2px rgba(190, 190, 190, 0.5) !important;opacity: 0.85 !important;color:#ffffff !important;}</style><link href="https://fonts.googleapis.com/css?family=Cookie" rel="stylesheet"><a target="_blank" class="bmc-button" href="https://www.buymeacoffee.com/T4KDHBPV6"><img src="https://www.buymeacoffee.com/assets/img/BMC-btn-logo.svg" alt="Buy me a coffee"><span style="margin-left:5px">Buy me a coffee</span></a>  
> If you like this app, please consider buying me a coffee. :relaxed:

## Use on Docker

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

## ScreenShots

### Timer Modal
![Timer Modal](./docs/images/home_screen.png)
### Calendar
![Calendar](./docs/images/calendar_screen.png)
### Report
![Report](./docs/images/report_screen.png)

## How does it working?
![Architecture](./docs/images/architecture.png)

- API container serve RESTful API and OAuth2 authentication.
- Web container send HTML/CSS/JS to browser. and fetch JSON from API server on a background.

## Related Repositories
- [ktmouk/hackaru-web](https://github.com/ktmouk/hackaru-web)
- [ktmouk/hackaru-api](https://github.com/ktmouk/hackaru-api)

## Feedback
- If you found bad English :memo:, or have a new idea :bulb:, Please send PullRequest! :relaxed:

## License
- [MIT](./LICENSE)
