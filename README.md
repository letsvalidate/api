### API for generating thumbnails of captured screenshots of websites.

    /v1/thumbs/

Name    | Default   | Description
----    | -------   | -----------
url     |           | Target URL (**required**), http(s):// prefix is optional
output  | raw       | Output format (raw, json)

more options? open an issue

Example (command line):

    $ curl -s https://api.letsvalidate.com/v1/thumbs?url=kontaktify.com > kontaktify.jpg

Example (web browser):

    https://api.letsvalidate.com/v1/thumbs/?url=kontaktify.com



### API for analyzing technologies of websites.

    /v1/technologies/

Name    | Type      | Description
----    | ----      | -----------
url     | string    | Target URL (**required**), http(s):// prefix is optional

Example:

    https://api.letsvalidate.com/v1/technologies/?url=kontaktify.com


### Notes

The current API rate limit is 100/1 calls/minute per client's ip address.

All generated thumbnails will be host CloudFlare CDN

Internally I use [Wappalyzer](https://github.com/AliasIO/Wappalyzer) for analyzing technologies of websites

