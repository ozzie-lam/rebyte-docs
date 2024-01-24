# You.com search

With this "You.com" search action, you can go and search anything.

### Description

Search the web using You.com API, you should put your search query in the "query" and you will get your results in seconds!

### spec

| Parameter         | Description                                   |
| ----------------- | --------------------------------------------- |
| query             | query sent to You.com                         |

### Output

* The output is a bit complex, it's a JSON object with two fields:"hits" and "latency". 

* The search results are in the "hits" field, it's an array with 10 most related search results.


