- In the auto-generated template, we have already created some actions for you.
- Add a "Knowledge Search" action using the plus button between different actions.

![截屏2024-01-11 17.23.06.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1596656e-c582-4668-acbb-9a7961ffa944/269abe87-45a9-4b7a-bbcc-5241e1805e0e/%E6%88%AA%E5%B1%8F2024-01-11_17.23.06.png)

- Choose the knowledge base you just created and set the number of results. This action allows you to perform a search on the given knowledge base and return the results.
- You can see all the search results in the chunks.

![截屏2024-01-11 17.12.21.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1596656e-c582-4668-acbb-9a7961ffa944/2afe043f-fc83-4769-bd00-b5d5d358f393/%E6%88%AA%E5%B1%8F2024-01-11_17.12.21.png)

- For better usage, we have three "Code" actions in this agent.
    - The first one is to extract content from the latest message.
        
        ![截屏2024-01-11 17.25.30.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1596656e-c582-4668-acbb-9a7961ffa944/74c3a41c-0167-4643-b1cb-d09ed2047970/%E6%88%AA%E5%B1%8F2024-01-11_17.25.30.png)
        
    - The second "Code" action is to concatenate the results from the "Knowledge Search" action.
        
        ![截屏2024-01-11 17.25.59.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1596656e-c582-4668-acbb-9a7961ffa944/fa6e3762-d013-4dcd-b338-22c4746a832e/%E6%88%AA%E5%B1%8F2024-01-11_17.25.59.png)
        
    - We use another "Code" action called "Generate Answer" to concatenate the search results and the response.
        
        ![截屏2024-01-11 17.26.22.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/1596656e-c582-4668-acbb-9a7961ffa944/ad970fae-83ca-445e-889b-f3d917183b22/%E6%88%AA%E5%B1%8F2024-01-11_17.26.22.png)
        
- Now use a "Language Model Chat Interface" action to get a response based on the search results.
- Write the instructions for the model in the editor, describing what you want the model to do. And the model will generate a response for you.
