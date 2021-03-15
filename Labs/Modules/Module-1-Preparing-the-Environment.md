# Module 1 – Preparing the Environment

<p align="left"><img src="../Images/asc-labs-beginner.gif?raw=true"></p>

#### 🎓 Level: 100 (Beginner)
#### ⌛ Estimated time to complete this lab: 30 minutes



#### Instructions:
1. Open an **In-Private** session in your web browser and navigate to https://azure.microsoft.com/en-us/free
2. On the main part of this page, click **Start free** and use your Microsoft Account credentials to you to login to Azure Portal.
Important - Make sure you are not logged in with your corporate user.
3. Type your Microsoft Account email address and then click on **Next**.
4. On the **Stay signed in** message, click **Yes**.
5. At the **Try Azure for free** page, type in your details following the 4-steps (your profile, identity verification by phone, identity verification by card, agreement). Once you complete all steps, click on **Sign Up** button to complete the subscription creation process.
6. On the **You’re ready to start with Azure** page, click on **Go to portal** button. Now you should have Azure Subscription named **Azure subscription 1** including owner permissions.

### Exercise 1: Enabling Azure Defender

#### Subscription upgrade and agents installation
1. Open **Azure Portal** and navigate to **Security Center** blade.
2. Click on **Getting started** page from the left pane, On the **Upgrade** Tab, select subscription (Azure subscription 1) and press **Upgrade**.
3. Click on **Install agents**, if the button has been grayed out, then it's already set to **On**.
4. Return to Azure security Center blade and Click on **Pricing & settings**.
5. Your subscription (Azure subscription 1) should be listed and Azure Defender plan should be **On (partial)** (if it does not, close your browser session and open a new one).

> Notice that you enabled Azure Defender at a subscription level, but Log Analytics workspace pricing is still set on Free (means Azure Defender is OFF).

#### Configure the data collection settings in ASC
1. On **Pricing and Settings** page, press on the Log Analytics workspace named **asc-lab-xxx**

![Template deployment completed](../Images/asc-workspace-pricing-settings.gif?raw=true)

2. On the Azure Defender Plans page, select **Azure Defender on** and press **Save**. Now both subscription and Log Analytics workspace should be set to **On** for Azure Defender plan.

![Enable Azure Defender on the workspace level](../Images/asc-enable-defender-workspace.gif?raw=true)

3. Go back to the **Pricing & Setting** and drill down into your **Azure subscription** (Azure subscription 1).
4. Navigate to **Data Collection**
5. On the **Auto provisioning - Extensions** page, set **Log Analytics agent for Azure VMs** to **On** (if it's not already set to On)
6. Click **Edit configuration**.
7. On the workspace configuration section, use the **Connect Azure VMs to a different workspace** option to select your workspace **asc-lab-xxx** (which has been created by the ARM template).
8. Under **Store additional raw data - Windows security events** section, select **All Events** option.

![Enable Azure Defender on the workspace level](../Images/asc-extension-deployment-configuration.gif?raw=true)

9. Click on **Apply**.
10. Click on **Save**.

<br>

> Please notice:
> * To get the full functionality of Azure Security Center and Azure Defender, both subscription and Log Analytics workspace should be enabled for Defender. Once you enable it, under the hood the required Log Analytics solutions will be added to the workspace.
> * Before clicking on the Upgrade button, you can review the total number of resources you are going to enable Azure Defender on.
> * You can enable Azure Defender trial for 30-days on a subscriptions only if not previously used.
> * To enable Azure Defender on a subscription, you must be assigned the role of Subscription Owner, Subscription Contributor, or Security Admin.

### Continue with the next lab: [Module 2 - Exploring Azure Security Center](../Modules/Module-2-Exploring-Azure-Security-Center.md)
