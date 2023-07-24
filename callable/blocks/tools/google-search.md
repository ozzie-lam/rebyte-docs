# Google Search

Find the most relevant links based on the Query through a google search

<figure><img src="../../../.gitbook/assets/Screenshot 2023-07-21 at 5.15.25 PM.png" alt=""><figcaption></figcaption></figure>

Parameters:

* **Number of Results:** Specifies how many organic results will be returned
* **Query:** Specify the question to search on google.

Return:

* **search\_metadata**: This contains meta-information about the search.
  * **id**: Unique identifier for the search
  * **status**: Status of the search operation (e.g., success or fail)
  * **json\_endpoint**: Endpoint to get the search result in JSON format
  * **created\_at**: When the search operation was created
  * **processed\_at**: When the search operation was processed
  * **google\_url**: The Google URL used for the search
  * **raw\_html\_file**: Raw HTML file of the search result
  * **total\_time\_taken**: Total time taken for the search operation
* **search\_parameters**: This includes the parameters used for the search.
  * **engine**: The search engine used
  * **q**: The query string for the search
  * **google\_domain**: The Google domain used for the search
  * **num**: The number of results desired
  * **device**: The device used for the search (e.g., desktop, mobile)
* **search\_information**: This provides additional information about the search.
  * **organic\_results\_state**: State of the organic results (e.g., available, not available)
  * **query\_displayed**: The query that was displayed
  * **total\_results**: The total number of search results
  * **time\_taken\_displayed**: Time taken to display the results
  * **spelling\_fix**: Any spelling corrections made for the search query
  * **showing\_results\_for**: If the search engine suggested a different search query
  * **menu\_items**: Additional options provided by the search engine for this query
* **knowledge\_graph**: This includes structured and detailed information about the search result.
  * Contains parameters like title, type, kgmid, tabs, header\_images, directions, description, local\_map, rating, review\_count, source, elevation, first\_ascent, prominence, location, meter, first\_ascenders, mountain\_range, mount\_everest\_mountaineers, animals\_mount\_everest and their associated links
* **inline\_people\_also\_search\_for**: Number of related search queries by other users
* **answer\_box**: This is the direct answer for the query from the search engine.
  * Contains parameters like type, title, link, answer, thumbnail, and people\_also\_search\_for
* **organic\_results**: The number of organic (non-sponsored) search results
* **related\_searches**: The number of related search queries
* **pagination**: Information about the pagination of the search results.
  * Contains parameters like current page, next page, and other pages
* **serpapi\_pagination**: Information about the pagination of the search results in the SERP API.
  * Contains parameters like current page, next\_link, next page, and other pages

