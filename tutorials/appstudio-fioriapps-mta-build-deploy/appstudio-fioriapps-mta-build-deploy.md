---
parser: v2
auto_validation: true
time: 20
tags: [ tutorial>beginner, software-product>sap-business-technology-platform, software-product>sap-fiori, programming-tool>sapui5, software-product>sap-btp-cloud-foundry-environment]
primary_tag: software-product>sap-business-application-studio
author_name: Raz Korn
author_profile: https://github.com/raz-korn
---

# Build and Deploy Your SAP Fiori App to SAP Business Technology Platform
<!-- description --> Build and deploy your SAP Fiori MTA project to your SAP BTP, Cloud Foundry environment.

## Prerequisites
- The SAP Fiori dev space is in status `RUNNING` and you opened it.
- You completed [Create an SAP Fiori App Using SAP Business Application Studio](appstudio-fioriapps-create).
- Make sure you have completed all steps listed in [Set Up SAP Business Application Studio for Development](https://developers.sap.com/tutorials/appstudio-onboarding.html). Especially adding all required entitlements is important.

## You will learn
  - How to build and deploy an application to SAP BTP, Cloud Foundry environment
  - How to configure Cloud Foundry settings in SAP Business Application Studio
  - How to run the deployed app from your space on SAP BTP, Cloud Foundry environment

## Intro
After a period of idle time the dev space is automatically stopped. In order to re-start the dev space open the **dev space manager** of SAP Business Application Studio and click the **Play** icon. When the dev space is in state **RUNNING**, click on the dev space name.

The period for idle time for Factory accounts is different than for trial accounts.

### Build the application

1. In the **Explorer** pane, right-click the `mta.yaml` file and select **Build MTA Project**.

    <br><br><!-- border -->![build mta](BAS-Build-1-.png)

    >The build process creates a multi-target archive (`MTAR`) file in your project that packages all the project modules for deployment. You can find the `MTAR` file in the `FioriDemo/mta_archives` folder.

    <!-- border -->![terminal mbt build results](BAS-Build-2-.png)


### Set Cloud Foundry preferences

If you are not logged in to a Cloud Foundry space, before you can deploy your new application, set your Cloud Foundry preferences.

1. In the left side bar, select the **Hamburger icon | View | Command Palette…** to open the **command palette**.

    <!-- border -->![Command Palette-Login to CF](BAS-CF-Login-1-.png)    

2. Select the command **CF: Login to cloud foundry**.

    >Type `cf` to filter commands.

    <!-- border -->![Command Palette-Login to CF](BAS-CF-Login-2-.png)

3. A **Cloud Foundry Sign In** tab opens in SAP Business Application Studio. Select your API endpoint.

    <!-- border -->![Cloud Foundry Login dialog](BAS-CF-Login-3-.png)
    
    If you don't know your API endpoint open the SAP Business Technology Platform Cockpit and navigate to your subaccount. Click on **Overview** on the left and you can see the URL of the **API endpoint** under **Cloud Foundry Environment**.

    <!-- border -->![Cloud Foundry Login dialog](BAS-CF-Login-3-1.png)

4. Select authentication method as **SSO Passcode**.

    Choose the link **Open a new browser page to generate your SSO passcode**.

    Sign in with the appropriate identity provider, and copy the **Temporary Authentication Code**.

    Enter the Temporary Authentication Code as **SSO Passcode**.

    Choose **Sign in**.

    <!-- border -->![Cloud Foundry Login dialog](BAS-CF-Login-3-.png)

5. Select the **Cloud Foundry organization**, **Cloud Foundry Space**, and click **Apply**.

    If the Cloud Foundry Target dropdowns are empty you need to change the default Cloud Foundry Endpoint to the one of your subaccount (see previous step). To obtain your subaccount's Cloud Foundry Endpoint open the SAP Business Technology Platform Cockpit and navigate to your subaccount. Click on Overview on the left and you can see the URL of the API endpoint under **Cloud Foundry Environment**.

    If the dropdown for Select Cloud Foundry Space is empty, check if you have created the needed Cloud Foundry Space as described in the section **Create your Trial Space** in [Setting Up Your Trial Account](https://help.sap.com/docs/btp/sap-business-technology-platform/cf-env-setting-up-your-trial-account?locale=f16df12fab9f4fe1b8a4122f0fd54b6e.html).

    <!-- border -->![Cloud Foundry Login dialog](BAS-CF-Login-4-.png)

    A notification **You have been logged in.** appears at the bottom-right of your screen.

    <!-- border -->![Logged in to CF](BAS-CF-Login-5-.png)


### Deploy the application

Deploy your application to SAP BTP, Cloud Foundry environment.

1. In the **Explorer** pane under the folder `mta_archives`, right-click the `mtar` file and select **Deploy MTA Archive**.

    <!-- border -->![deploy mtar](BAS-Deploy-1-.png)

    >The application deployment to the space you are connected to starts and a notification appears. You can follow the deployment progress in the **Task: Deploy** console at the bottom of your screen.

2. Wait for the deployment to complete.

    >The deployment process takes a few minutes. When the deployment process is complete, the notifications **Process finished.** and **Terminal will be reused by tasks.** will appear at the bottom of the **Task: Deploy** console.

    ><!-- border -->![deploy success](BAS-Deploy-2-.png)

    If you have issues with the deployment, check out the [SAP Business Application Guided Answers](https://ga.support.sap.com/dtp/viewer/index.html#/tree/2827/actions/41344) for troubleshooting.


### Open the application

1. Go back to your SAP BTP Trial account and click the button **Go To Your Trial Account**. 

<!-- border -->![deploy mtar](BAS-Open-1-.png)

2. Click the trial tile to navigate to your trial subaccount in the SAP BTP cockpit. 

<!-- border -->![deploy mtar](BAS-Open-2-.png)

3. Select **HTML5 Applications** in the left navigation panel.

<!-- border -->![deploy mtar](BAS-Open-3-.png)

4. You will see a list of all HTML5 Application you deployed up to now. Select the one you deployed in the previous step.

<!-- border -->![deploy mtar](BAS-Open-4-.png)

Congratulations!

With this, you have successfully completed the deployment of your SAP Fiori app to SAP BTP using SAP Business Application Studio.

In this tutorial, you used high productivity tools that are available out-of-the-box in SAP Business Applications Studio that make it easy to build and deploy applications as well as work in the Cloud Foundry environment.


---
