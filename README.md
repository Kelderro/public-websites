# Example static website with Docker, Nginx and Certbot

This is full project structure example of article **How to dockerize your static website with Nginx, automatic renew SSL for domain by Certbot and deploy it to DigitalOcean?**

Published on [Dev.to](https://dev.to/koddr/how-to-dockerize-your-static-web-site-and-deploy-it-to-digitalocean-with-nginx-and-automatic-renew-ssl-by-certbot-43bp-temp-slug-9047717) @ 27 Jan 2020.

## Requirements

- Docker `19.x+`

## Usage

- Clone this repository and go to folder:

```console
git clone https://github.com/koddr/example-static-website-docker-nginx-certbot.git
cd example-static-website-docker-nginx-certbot
```

- Change `site.com` to your domain at files:

```console
./docker-compose.prod.yml
./webserver/nginx/default.conf
./webserver/nginx/site.com.conf
```

- Push configured project to your own git repository.
- Go to DigitalOcean account, create and configure new droplet.
- Connect via SSH to your droplet and `git clone` your repo.
- Check configuration of `Certbot`, start the process of obtaining SSL certificate in test mode:

```console
make certbot-test DOMAINS="site.com www.site.com" EMAIL=mail@site.com
```

- If you see `Congratulations!`, all okay; start the process of obtaining SSL in production mode:

```console
make certbot-prod DOMAINS="site.com www.site.com" EMAIL=mail@site.com
```

- And now, check Nginx config:

```console
make deploy-test
```

- No errors? Go your static website to production:

```console
make deploy-prod
```

- That's all!

## Author

- [Vic Shóstak](https://github.com/koddr) (aka Koddr).

## Article assistance

If you want to say «thank you»:

1. Twit about article [on your Twitter](https://twitter.com/intent/tweet?text=).
2. Add a GitHub Star and make Fork to this repository.
3. Donate some money to project author via PayPal: [@paypal.me/koddr](https://paypal.me/koddr?locale.x=en_EN).
4. Join DigitalOcean at our [referral link](https://m.do.co/c/b41859fa9b6e) (your profit is **$100** and we get $25).

Thanks for your support! 😘

## License

MIT