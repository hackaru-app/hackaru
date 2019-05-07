<div style="text-align: center; margin: 40px 0;">
  <img src="./docs/images/logo.png" width="26" style="margin: 20px" />  
  <p style="color: #666;">Manage your meaningful time.</p>
</div>

## What's Hackaru?
Hackaru is the simple time tracking application.
> Hackaru (測る) means "Measure" in Japanese.

## Screens

<img src="./docs/images/home_screen.png" width="400" style="border: 1px #eee solid; padding: 5px; border-radius: 5px; margin: 20px" />  
<img src="./docs/images/calendar_screen.png" width="400" style="border: 1px #eee solid; padding: 5px; border-radius: 5px; margin: 20px" />  
<img src="./docs/images/report_screen.png" width="400" style="border: 1px #eee solid; padding: 5px; border-radius: 5px; margin: 20px" />  

## Features

- [PWA](https://developers.google.com/web/progressive-web-apps/)  support. You can use on iOS and Android.
- OAuth 2.0 provider support.
- Webhook Support (e.g., Timer started, Timer stopped)
- Open-source. You can build on your server.
- You can time automatically you are using favorite Applications. See [Hackaru for Desktop](https://github.com/ktmouk/hackaru-desktop)

## How to use?
You can use Hackaru on the official website. It's free.
- https://www.hackaru.app

## Use Docker

Run this commands, And access http://localhost:3000
```
git clone https://github.com/ktmouk/hackaru.git && \
cd ./hackaru && \
cp .env.api.sample .env.api && \
cp .env.web.sample .env.web && \
echo "SECRET_KEY_BASE=$(docker-compose run --rm api rails rake:secret)" >> .env.api && \
echo "JWT_SECRET=$(docker-compose run --rm api rails rake:secret)" >> .env.api && \
docker-compose run --rm api rails db:create db:migrate && \
docker-compose up
```

## Repos
- [ktmouk/hackaru-web](https://github.com/ktmouk/hackaru-web)
- [ktmouk/hackaru-api](https://github.com/ktmouk/hackaru-api)
- [ktmouk/hackaru-desktop](https://github.com/ktmouk/hackaru-desktop)

## License
- [MIT](./LICENSE)

## Donation
<a href="https://www.buymeacoffee.com/T4KDHBPV6"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: auto !important;width: auto !important;" ></a>  
