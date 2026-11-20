# WooCommerce robots.txt for SEO and site speed

A ready-to-use `robots.txt` for WooCommerce stores, maintained by [WP Speed Fix](https://www.wpspeedfix.com/).

WooCommerce sites attract aggressive crawling. Bots follow add-to-cart links, search results, sort orders and currency switchers, and every one of those requests is uncached and hits PHP and the database. On a busy store that wastes crawl budget and can push CPU high enough to slow the site for real customers.

Full write-up, with the reasoning behind each rule: **[WooCommerce robots.txt File For Better SEO & Site Speed](https://www.wpspeedfix.com/woocommerce-robots-txt/)**

## What it does

| Rule | Why |
|---|---|
| `Crawl-delay: 5` | Slows down crawlers that honour it, so they can't hammer the server |
| Block `/wp-admin/`, `wp-login.php`, `/my-account/` | Login and account pages have no search value |
| Block `?s=` and `/search/` | Internal search results create endless thin, duplicate URLs |
| Block `add-to-cart` and `add_to_wishlist` | Some themes link to these directly, and each crawl runs an uncached cart action |
| Block `currency=` and `?orderby` | Sort and currency variants duplicate your category pages |
| Block `/feed/` | WordPress feeds duplicate your content |
| Block `wp-toolkit` | Stops crawling of Plesk and cPanel smart update test copies |
| Allow `/wp-admin/admin-ajax.php` | Needed because `/wp-admin/` is blocked above |
| Block AhrefsBot and SemrushBot | Heavy third-party SEO crawlers that don't send you customers |

## How to use it

1. Download [`robots.txt`](robots.txt).
2. Change the `Sitemap:` line to your own sitemap URL.
3. If your theme has sidebar filters (size, colour, price), add `Disallow` lines for those query strings too.
4. Upload it to the root of your site so it loads at `https://yourdomain.com/robots.txt`. If you use Yoast or Rank Math, you can paste it into their robots.txt editor instead.
5. Test it in Google Search Console's robots.txt report.

## Notes

- Google ignores `Crawl-delay`. Bing, Yandex and most other crawlers respect it.
- robots.txt is a request, not a wall. Bad bots ignore it, so pair it with firewall rules. The post covers using Cloudflare for that.
- Don't put search or filter URLs in your menus. Crawlers will follow them however you set up robots.txt.

## Need help with a slow WooCommerce store?

[WP Speed Fix](https://www.wpspeedfix.com/) speeds up and supports WordPress and WooCommerce sites.
