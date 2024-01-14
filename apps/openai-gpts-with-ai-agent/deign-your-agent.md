- In the auto-generated template, we have already created some actions for you.
- Add a "Knowledge Search" action using the plus button between different actions.


<figure><img src="../../images/deign-your-agent-1.png"></figure>

- Choose the knowledge base you just created and set the number of results. This action allows you to perform a search on the given knowledge base and return the results.
- You can see all the search results in the chunks.

<figure><img src="../../images/deign-your-agent-2.png"></figure>

- For better usage, we have three "Code" actions in this agent.
    - The first one is to extract content from the latest message.
        
        <figure><img src="../../images/deign-your-agent-3.png"></figure>
        
    - The second "Code" action is to concatenate the results from the "Knowledge Search" action.
        
        <figure><img src="../../images/deign-your-agent-4.png"></figure>
        
    - We use another "Code" action called "Generate Answer" to concatenate the search results and the response.
        
        <figure><img src="../../images/deign-your-agent-5.png"></figure>
        
- Now use a "Language Model Chat Interface" action to get a response based on the search results.
- Write the instructions for the model in the editor, describing what you want the model to do. And the model will generate a response for you.
<figure><img src="../../images/deign-your-agent-6.png"></figure>
