# Chat with Notion

Today I'm going to show you how to use Notion pages as a knowledge base for GPT.

## Step 1: Create Knowledge with Notion

- Navigate to the Knowledge page and create a new knowledge.

<figure><img src="../../images/%25E6%2588%25AA%25E5%25B1%258F2024-01-11_16.58.50.png"></figure>


- Fill in the name and description of the knowledge.

<figure><img src="../../images/%25E6%2588%25AA%25E5%25B1%258F2024-01-11_16.58.50.png"></figure>

- Since we are using Notion as the knowledge base, we need to select `Notion` as the knowledge source.

<figure><img src="../../images/%25E6%2588%25AA%25E5%25B1%258F2024-01-11_17.00.17.png"></figure>

- Choose a chunk size and create knowledge.

- Connect your Notion account to ReByte and choose the page you want to use.

<figure><img src="../../images/%25E6%2588%25AA%25E5%25B1%258F2024-01-11_17.01.41.png"></figure>


<figure><img src="../../images/%25E6%2588%25AA%25E5%25B1%258F2024-01-11_17.01.41%201.png"></figure>


- Now you should have your knowledge of the content from Notion.

<figure><img src="../../images/%25E6%2588%25AA%25E5%25B1%258F2024-01-11_17.04.55.png"></figure>

## Step 2: Clone Agent

- In Community select the tab "GPT Builder Actions" and click “knowledge_search_agent_for_gpts”

<figure><img src="../../images/Untitled.png"></figure>

- copy it to your own project
  
<figure><img src="../../images/Untitled%201.png"></figure>


## Step 3: Select your knowledges and **Deploy it**

- Find the action called RETRIEVALS and select the knowledge you created


<figure><img src="../../images/Untitled%202.png"></figure>

- Run TestCases and deploy it

If you're interested in how to design this agent, you can check it out by clicking on the following page

[deign your Agent](./design-your-agent)

## Step 4: Create GPTs with ReByte API

- Fill in the name, description, and avatar for your GPTs.


<figure><img src="../../images/Untitled%203.png"></figure>

- Copy and paste the OpenAPI code for the corresponding version of your ReByte Agent into the Action of GPTs, and set **Authentication** as API Key.

<figure><img src="../../images/Untitled%204.png"></figure>

<figure><img src="../../images/Untitled%205.png"></figure>

- Fill in ReByte's API key (**Select Bearer for Auth Type**).

<figure><img src="../../images/Untitled%206.png"></figure>

- Save and release your GPTs!
- Now you can use it!


<figure><img src="../../images/Untitled%207.png"></figure>

<figure><img src="../../images/Untitled%208.png"></figure>
