# Web scrawler

We provide a built-in HTTP web crawler that will recursively traverse most links from the root URL. Just provide the root URL and we will automatically start crawling. More information about its behavior:

- We will try to fetch the sitemap from the root URL and import the first 100 URLs, which you can delete those you do not want.
- We only index the first 20K characters of each page.
- It works very well if your web pages are server-side rendered, but not as well if it is a SPA, we are working on it. Note: This type cannot be modified after creation.