> You can follow us on [Twitter](https://twitter.com/letsvalidate) or subscribe to our [newsletter](http://eepurl.com/cMQjGz) for upcoming updates.


### API for generating thumbnails of captured screenshots of websites.

    /v1/thumbs/

Name           | Default            | Accepted Value        | Description
----           | -------            | --------------        | -----------
url            |                    | Any valid URLs        | Target URL (**required**), http(s):// prefix is optional
output         | raw                | raw, json             | Output format (raw, json)
prettify       | false              | Any boolean values    | Prettify JSON output
format         | jpg                | jpg, jpeg, png        | Image format (jpg, png)
quality        | 100                | 1..100                | Image quality
full           | false              | Any boolean values    | Capture full page
size           |                    | t, s, m, l, x, og     | The size of the thumbnail. Available predefined sizes: **t** - Tiny (90x68), **s** - Small (120x90), **m** - Medium (200x150), **l** - Large (400x300), **x** - Extra large (480x360), **og** - Recommended image size of Facebook's Open Graph protocol (1200x630)
width          | 320                | 1..16383              | The width of the thumbnail
height         | 240 (mobile: 568)  | 1..16383              | The height of the thumbnail
mobile         | false              | Any boolean values    | Whether to emulate mobile device. This includes viewport meta tag, overlay scrollbars, text autosizing and more
device         |                    | See the below list    | Predefined user agent, viewport width & height, ...
viewportWidth  | 1200 (mobile: 412) | 1..1600               | The viewport width of the page
viewportHeight | 1200 (mobile: 732) | 1..1600               | The viewport height of the page
userAgent      |                    | Any valid user agents | Not yet implemented
delay          |                    | 0..10                 | Not yet implemented


more options? open an issue

Example (command line):

    $ curl -s https://api.letsvalidate.com/v1/thumbs?url=kontaktify.com > kontaktify.jpg

Example (web browser):

    https://api.letsvalidate.com/v1/thumbs/?url=kontaktify.com

<details>

  <summary>Result:</summary>
  
  <img src="https://api.letsvalidate.com/v1/thumbs/?url=kontaktify.com" width="320" height="240" alt="Kontaktify Preview">
</details>


Example (json output):

    https://api.letsvalidate.com/v1/thumbs/?url=kontaktify.com&output=json
    
<details>

  <summary>Result:</summary>

```json
{
	"mime_type": "image/jpeg",
	"base64": "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",
	"width": 320,
	"height": 240
}
```
</details>

Example of using `og` size with the following HTML code.

```html
<!-- Put additional og tags here -->
<meta property="og:image" content="https://api.letsvalidate.com/v1/thumbs?url=kontaktify.com&size=og" />

<!-- The same image also works for twitter card -->
<!-- Put additional twitter card tags here -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:image" content="https://api.letsvalidate.com/v1/thumbs?url=kontaktify.com&size=og" />
```

<details>

  <summary>A list of accepted devices:</summary>

```  
galaxys5
nexus5x
nexus6p
iphone5
iphone6
iphone6plus
ipad
ipadpro
iphone4
ipadmini
nokian9
nokialumia520
nexus7
nexus6
nexus5
nexus4
nexus10
microsoftlumia950
microsoftlumia550
blackberryz30
blackberryplaybook
galaxynote3
galaxynoteii
galaxysiii
kindlefirehdx
lgoptimusl70
laptopwithtouch
laptopwithmdpiscreen
laptopwithhidpiscreen
```
</details>

### API for analyzing technologies of websites.

    /v1/technologies/

Name     | Type      | Default | Description
----     | ----      | ------- | -----------
url      | string    |         | Target URL (**required**), http(s):// prefix is optional
prettify | boolean   | false   | Prettify JSON output

Example:

    https://api.letsvalidate.com/v1/technologies/?url=kontaktify.com

<details>

  <summary>Result:</summary>

```json
{
	"url": "https://www.kontaktify.com",
	"originalUrl": "http://kontaktify.com",
	"applications": [{
		"name": "BuySellAds",
		"confidence": "100",
		"version": "",
		"icon": "BuySellAds.png",
		"website": "http://buysellads.com",
		"categories": ["Advertising Networks"]
	}, {
		"name": "Carbon Ads",
		"confidence": "100",
		"version": "",
		"icon": "Carbon Ads.png",
		"website": "http://carbonads.net",
		"categories": ["Advertising Networks"]
	}, {
		"name": "CloudFlare",
		"confidence": "100",
		"version": "",
		"icon": "CloudFlare.svg",
		"website": "http://www.cloudflare.com",
		"categories": ["CDN"]
	}, {
		"name": "Facebook",
		"confidence": "100",
		"version": "",
		"icon": "Facebook.svg",
		"website": "http://facebook.com",
		"categories": ["Widgets"]
	}, {
		"name": "Google Analytics",
		"confidence": "100",
		"version": "UA",
		"icon": "Google Analytics.svg",
		"website": "http://google.com/analytics",
		"categories": ["Analytics"]
	}, {
		"name": "Google Font API",
		"confidence": "100",
		"version": "",
		"icon": "Google Font API.png",
		"website": "http://google.com/fonts",
		"categories": ["Font Scripts"]
	}, {
		"name": "Hotjar",
		"confidence": "100",
		"version": "",
		"icon": "Hotjar.png",
		"website": "https://www.hotjar.com",
		"categories": ["Analytics"]
	}, {
		"name": "Kontaktify",
		"confidence": "100",
		"version": "",
		"icon": "Kontaktify.png",
		"website": "https://www.kontaktify.com",
		"categories": ["Widgets"]
	}, {
		"name": "Nginx",
		"confidence": "100",
		"version": "",
		"icon": "Nginx.svg",
		"website": "http://nginx.org/en",
		"categories": ["Web Servers"]
	}, {
		"name": "React",
		"confidence": "100",
		"version": "",
		"icon": "React.png",
		"website": "http://facebook.github.io/react",
		"categories": ["JavaScript Frameworks"]
	}, {
		"name": "Twitter",
		"confidence": "100",
		"version": "",
		"icon": "Twitter.svg",
		"website": "http://twitter.com",
		"categories": ["Widgets"]
	}, {
		"name": "Twitter Bootstrap",
		"confidence": "100",
		"version": "",
		"icon": "Twitter Bootstrap.png",
		"website": "http://getbootstrap.com",
		"categories": ["Web Frameworks"]
	}, {
		"name": "Zepto",
		"confidence": "100",
		"version": "",
		"icon": "Zepto.png",
		"website": "http://zeptojs.com",
		"categories": ["JavaScript Frameworks"]
	}]
}
```
</details>

### Notes

* The current API rate limit is 100/1 calls/minute per client's ip address.

* All generated thumbnails will be host CloudFlare CDN and serve over https, and without any watermarks.

* Internally I use [Wappalyzer](https://github.com/AliasIO/Wappalyzer) for analyzing technologies of websites.

* Currently for accessing the APIs no need any keys.

* The thumbnailing handles all modern websites.

* Using [headless chrome](https://chromium.googlesource.com/chromium/src/+/lkgr/headless/README.md) for capturing screenshots. 
