# **Lab 6 : Secure Generative AI Applications**

## Overview:

In this lab, we'll explore the steps involved in securing generative AI applications by implementing robust content filters and security measures. The lab guides you through enabling AI workload plans in Microsoft Defender for Cloud, validating and creating content filters, and exploring the Azure AI Foundry portal for managing deployments. You will learn how to mitigate risks associated with jailbreak attacks by setting up advanced security features and monitoring alerts in the Azure portal. By the end of this lab, you’ll gain hands-on experience in securing AI models to ensure they operate safely and comply with organizational policies.

## Estimated Duration: 50 min

## Lab objectives : 

In this lab, you will complete the following tasks:

- Enable AI workload plan
- Explore Azure AI Foundary portal
- Validate Content Filter Policy
- Create The Content Filter

## **Task 1: Enable AI workload plan**

1. In the search bar, type **Microsoft Defender (1)** and select **Microsoft Defender for Cloud (2)** from the results.

   ![](images/178.png)

1. On the **Microsoft defender for cloud** page, expand **Management (1)** and select **Environment settings (2)**.

   ![](./images/175.png)
   
1. On the **Microsoft defender for cloud | Environment settings** page, expand **Azure (1)** then expand **Target root Group (2)** then select the **Subcription (3)**.

   ![](./images/174.png)

1. On the **Settings | Defender plans** page, verify the Defender for Cloud configuration to ensure the AI Workload Plan is enabled.

   ![](./images/176.png)

1. Verify that the models have an active Content Filter Policy in place.

## **Task 2: Explore Azure AI Foundary portal**

1. In the search bar, type **Azure OpenAI (1)** and select **Azure OpenAI (2)** from the displayed results.  

   ![](./images/177.png)  

2. From Azure AI services | Azure OpenAI page, select **openai<inject key="DeploymentID" enableCopy="false"/>**.

   ![](./images/179.png)

1. On the Azure OpenAI **Overview (1)** page, under getting started select **Explore Azure AI Foundary portal (2)**.

   ![](./images/180.png)

1. Right-click on the [GitHub repository](https://github.com/0xk1h0/ChatGPT_DAN), select **Copy Link**, and paste it into a new tab in the egde browser.

1. Under **ChatGPT "DAN" (and other "Jailbreaks") PROMPTS**, expand **The DAN 6.0 Prompt (1)** and copy the content located under **DAN 6.0 Prompt (2)**.

   ![](./images/181.png)

1. Navigate back to the **Azure AI Foundry portal**. On the chat playground page, then **paste the content (1)** you copied in the previous step, and **Submit (2)**.

   ![](./images/182.png)

## **Task 3: Validate Content Filter Policy**

1. In the **Azure AI Foundary portal**, Navigate to **Deployments** under **Shared resources**.

1. Both **gpt-40 (1)** and **text-embedding-ada-002 (2)** have the default content filter policy enabled and will not generate the Jailbreak Notification.

   ![](./images/183.png)

## **Task 4: Create The Content Filter**

1. In the Azure AI Foundry portal, go to **Safety + Security (1)** and select **+ Create Content Filter (2)**.

   ![](./images/185.png)

1. Create the Content Filter with following details:

    - **Basic Information:**

      - Name: **CustomContentFilterWithJailBreakProtection (1)**
      - Click on **Next (2)**

        ![](./images/186.png)

    - **Input Filter:**

      - Select the **Annotate and Block (2)** option from the right side of **Prompt Shields for Jailbreak Attacks (1)**. Then, in the drop-down menu, choose **Off (2)** and click **Next (4)**.
 
        ![](./images/187.png)
  
    - **Output Filter:**

      - Leave as default and click on **Next**.

        ![](./images/188.png)

    - **Deployment (optional):**

      - Select all three deployments **(1)**, then click **Next (2)**.

       ![](./images/189.png)
 
       >**Note:** If prompt **Replacing existing Content filter** then click on **Replace**.

         ![](./images/190.png)

    - **Review:**

      - On the **Review** page, click **Create Filter**.

        ![](./images/191.png)

1. Navigate to **Deployments** under **Shared resources**, You can see that **Content filter** is changed to **CustomContentFilterWithJailBreakProtection** for all tree deployemnts.

   ![](./images/192.png)

1. In the Azure AI Foundry portal, go to **Playground** and select **Chat (1)**. Enter **What can you do? (2)** in the input field, then review the generated response **(3)**.

   ![](./images/193.png)

1. Under **ChatGPT "DAN" (and other "Jailbreaks") PROMPTS**, expand **The DAN 6.0 Prompt (1)** and copy the content located under **DAN 6.0 Prompt (2)**.

   ![](./images/181.png)

1. Navigate back to the **Azure AI Foundry portal**. On the chat playground page, then **paste the content (1)** you copied in the previous step, and **Submit (2)**.

   ![](./images/182.png)

1. Notice the response:

   ![](./images/194.png)

1. Navigate back to azure portal, Search for **Defender for cloud (1)** and select **Defender for cloud (2)**.

   ![](images/178.png)

1. Naviagte to **Security alerts** under **General**.

   ![](images/195.png)

1. Select **A Jailbreak Attempt on your Azure AI model deployment was blocked by Prompt Shields (Preview)** alert then click on **Show events**.

   ![](images/196.png)

1. Take note of the suspicious segment in the Application and Prompt.

   ![](images/197.png)

## **Summary:**

The tasks guide users to enable AI Workload Plan in Microsoft Defender for Cloud, explore the Azure AI Foundry portal, and validate content filter policies. Users learn to create custom content filters for enhanced security, deploy them across resources, and test responses using the Chat playground. Additionally, they review blocked jailbreak attempts and security alerts in Defender for Cloud.


## You have successfully completed the lab