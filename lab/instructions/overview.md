## Before You Begin

In any point of time during the lab, if you need to sign in to the virtual machine (Windows) or any Azure or Microsoft 365 apps (M365 Copilot, SharePoint, Teams etc.), use the credentials provided below.

### Sign into Virtual Machine (Windows)

If you need to sign in the virtual machine, use the following credentials:

- **User name**: +++@lab.VirtualMachine(Win11-Pro-Base).Username+++  
- **Password**: +++@lab.VirtualMachine(Win11-Pro-Base).Password+++

### Sign into Azure & Microsoft 365

If you need to sign in to any Azure or Microsoft 365 apps, use the following credentials:

- **Username**: +++@lab.CloudPortalCredential(User1).Username+++  
- **Temporary Access Pass**: +++@lab.CloudPortalCredential(User1).AccessToken+++

## Overview

In this hands-on lab, you'll build a knowledge base that can retrieve, reason, and respond over enterprise data using agentic retrieval in Azure AI Search.

Unlike traditional search or basic RAG systems that simply return documents, an agentic knowledge base plans how and where to search, chooses the most relevant knowledge sources, and synthesizes grounded, citation-backed responses tailored to the user's intent. This transforms retrieval into a dynamic, adaptive process that delivers deeper insights and more relevant answers.

By the end of this lab, you'll understand how agentic retrieval works and have hands-on experience with different knowledge base configurations and optimization strategies.

### What You'll Learn

In this lab, you'll work with agentic retrieval patterns to build knowledge bases that can intelligently query multiple data sources, plan retrieval strategies, and generate grounded responses with citations. You'll also learn how to optimize retrieval performance by adjusting reasoning effort levels.

## Getting Started

Follow the steps below to set up your environment and begin the lab.

### Sign into Windows

In the virtual machine, sign into Windows using the following credentials:

- **User name**: +++@lab.VirtualMachine(Win11-Pro-Base).Username+++  
- **Password**: +++@lab.VirtualMachine(Win11-Pro-Base).Password+++

### Access the Lab Repository

Once signed in to the Skillable environment, you’ll find the lab repository already cloned on your desktop under the folder: **Desktop > ignite25-lab511-private-dev**.

> This folder contains all the code, notebooks, and resources you’ll need for the lab.

### Open the Project Folder in Visual Studio Code

Open Visual Studio Code and select **File > Open Folder**. Then navigate to Desktop and select the **ignite25-lab511-private-dev** folder and then **Select Folder**.

> [!TIP]
> * When prompted whether to trust the authors of the files, select **Yes, I trust the authors**.

### Verify the Environment Setup

All required Azure services including **Azure AI Search with pre-indexed data** and **Azure OpenAI deployments** have already been provisioned for you.

**What's Pre-Configured:**
- **Azure AI Search** - Standard tier with two pre-created indexes:
  - **hrdocs:** HR policies, employee handbook, role library, company overview
  - **healthdocs:** Health insurance plans, benefits options, coverage details
- **Azure OpenAI** - Deployed models **gpt-4.1** for chat completion and answer synthesis and **text-embedding-3-large** for vector embeddings
- **Pre-computed vectors** - All 384 documents are already vectorized and indexed

#### Verify Environment Variables

1. Open the **.env** file under the main project folder.  
2. Verify that it includes the key environment variables *AZURE_SEARCH_SERVICE_ENDPOINT*, *AZURE_SEARCH_ADMIN_KEY*, *AZURE_OPENAI_ENDPOINT*, and *AZURE_OPENAI_KEY*.

If these variables are present, proceed to verify the indexes in Azure Portal.

#### Verify Indexes in Azure Portal

Let's confirm that the search indexes have been created successfully:

1. Open a web browser and navigate to the +++https://portal.azure.com+++.
2. Sign in using your lab credentials:
    - **Username**: +++@lab.CloudPortalCredential(User1).Username+++  
    - **Temporary Access Pass**: +++@lab.CloudPortalCredential(User1).AccessToken+++
3. In the Azure Portal search bar at the top, search for +++lab511-search+++ and select your AI Search service (it will look like *lab511-search-.....*).
4. In the left navigation menu, select **Search management** > **Indexes**.
5. You should see two indexes:
   - **hrdocs** - Should show approximately 50 documents
   - **healthdocs** - Should show approximately 334 documents

> **✅ Checkpoint:** If you see both indexes with document counts, your environment is ready! If the indexes are missing or empty, please notify your instructor.

If your indexes are present and populated, your environment is ready to use. You can now proceed to start with the Jupyter Notebooks.

### Start with Jupyter Notebooks

This lab includes 8 progressive notebooks covering different knowledge base patterns:

1. **Basic Knowledge Base** - Connect indexed data, configure Azure OpenAI, generate cited answers
2. **Multiple Knowledge Sources** - Query across indexes with custom instructions
3. **SharePoint Integration** - Real-time document retrieval from SharePoint
4. **Web Sources** - Combine internal and external content
5. **Blob Storage** - Upload and index with minimal vs. semantic strategies
6. **Combined Sources** - Unified querying across multiple source types
7. **Minimal Reasoning** - Speed-optimized retrieval
8. **Medium Reasoning** - Balanced query decomposition

**Start with `part1-basic-knowledge-base.ipynb`** in the `notebooks/` folder and progress through each notebook sequentially.

### Complete the Lab

Work through each notebook in order, starting with `part1-basic-knowledge-base.ipynb`. Each notebook explores a different knowledge base pattern and builds on concepts from previous parts.

Once you've completed all 8 notebooks, select **Next** to review key takeaways and next steps.
