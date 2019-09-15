# Xamarin Azure Challenge

Welcome to the Xamarin Azure Challenge.

The goal is to create an serverless [Azure Function](https://azure.microsoft.com/services/functions?WT.mc_id=xamarinazurechallenge-github-bramin), connect it to a [Xamarin](https://dotnet.microsoft.com/apps/xamarin?WT.mc_id=xamarinazurechallenge-github-bramin) mobile app.

### Challenge Objectives

1. Create and publish a serverless [Azure Function](https://azure.microsoft.com/services/functions?WT.mc_id=xamarinazurechallenge-github-bramin)
2. Add the Azure Function url to the [Xamarin.Forms](https://docs.microsoft.com/xamarin/xamarin-forms?WT.mc_id=xamarinazurechallenge-github-bramin) application
3. Submit your entry from the Xamarin.Forms application to your Azure Function

## Task 0: Prerequisites

1. Create Azure Suscription
    * If you do not currently have an Azure subscription, sign up for a [free Azure account](https://azure.microsoft.com/free?WT.mc_id=xamarinazurechallenge-github-bramin) that includes a $200 Azure Credit
2. Install Visual Studio + Xamarin Tools
    * On PC, [follow these steps to install Visual Studio with Xamarin](https://docs.microsoft.com/xamarin/get-started/installation/windows?WT.mc_id=xamarinazurechallenge-github-bramin)
    * On Mac, [follow these steps to install Visual Studio for Mac with Xamarin](https://docs.microsoft.com/visualstudio/mac/installation?view=vsmac-2019&WT.mc_id=xamarinazurechallenge-github-bramin)


## Task 1: Create and publish an Azure Function resource in Azure

### 1. Retrieve Source Code

We have two options to retrieve the code for the Xamarin Azure Challenge:
* Clone the repository
* Download the source code

#### 1a. Clone the repository

To [clone](https://git-scm.com/docs/git-clone) this repository, run this command in your favorite terminal:

``` bash
git clone https://github.com/xamarin/XamarinAzureChallenge.git
```

#### 1b. Download Source Code

To download the source clode, click this link: https://github.com/xamarin/XamarinAzureChallenge/archive/master.zip

### 2. Create Azure Function

After cloning the repository, we have 3 options to create and publish the Azure Function:

1. Use Visual Studio to [create](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio?WT.mc_id=xamarinazurechallenge-github-bramin) and [publish the Azure Function](https://blogs.msdn.microsoft.com/benjaminperkins/2018/04/05/deploy-an-azure-function-created-from-visual-studio?WT.mc_id=xamarinazurechallenge-github-bramin).
2. Use [Azure Portal to create the Azure Function](https://docs.microsoft.com/azure/azure-functions/functions-create-function-app-portal) and [Visual Studio to publish it](https://blogs.msdn.microsoft.com/benjaminperkins/2018/04/05/deploy-an-azure-function-created-from-visual-studio?WT.mc_id=xamarinazurechallenge-github-bramin)
3. Use [Azure CLI to create and publish the Azure Function](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli?WT.mc_id=xamarinazurechallenge-github-bramin)


#### 2a. Use Visual Studio to create and publish the Azure Function

> Prior to this step, ensure you have a valid Azure Subscription and are [logged into Visual Studio using your Azure account](https://docs.microsoft.com/visualstudio/ide/signing-in-to-visual-studio?view=vs-2019&WT.mc_id=xamarinazurechallenge-github-bramin#how-to-sign-in-to-visual-studio)

1. In Visual Studio go to the Solution Explorer and select XamarinAzureChallenge.Functions project.

![publish](https://user-images.githubusercontent.com/13558917/57552330-690b3280-7320-11e9-97e8-18531a238b5b.png)

 2. On the project, right-click and select **Publish**.

![start](https://user-images.githubusercontent.com/13558917/57552303-53960880-7320-11e9-958d-e44cf122bf6a.png)

3. In the Publish window, select **Azure Function App** > **Create New** > **Create Profile**

![start](https://user-images.githubusercontent.com/13558917/57551949-3280e800-731f-11e9-9d19-4f17b6a9c967.png)

4. In the **App Service Create New** window, input the following data:

- **Name**: XamarinAzureChallenge-[Your Last Name]
    - Note: The app name must be unique because it is used for the Azure Functions Url. This is why we'll append our Last Name.
- **Subscription**: [Select your Azure subscription]
- **Resource Group**: 
    - **New...**
        -  **New resource group name**: XamarinAzureChallenge
- **Location**: [Select the Azure Datacenter closest to you]
- **Azure Storage**: 
    - **New...**
        -  **Account name**: xamarinazurechallenge[Your Last Name]
            - Note: The Azure Storage Name must be unique which is why we append our Last Name.
        - **Location**: [Select the Azure Data Center closest to you]
        - **Account type**: Standard - Locally Rendundant Storage

![start](https://user-images.githubusercontent.com/13558917/57551835-e5047b00-731e-11e9-8feb-26a586e6f3af.png)

4. In the **App Service Create New** window, click on **Create**

5. Stand by while the Azure Function resource is created in Azure


#### 2b. Use Azure Portal to create the Azure Function and Visual Studio to publish it

1. In your broser, naviagte to the [Azure Portal](http://portal.azure.com?WT.mc_id=xamarinazurechallenge-github-bramin) 

2. In the **Azure Portal**, on the left-hand menu, click **+ Create a resource**

> Note: If the toolbar is collapsed, it will be shown as a green **+**

![Create new resource](https://user-images.githubusercontent.com/13558917/64928580-1a3e3f80-d7cf-11e9-84e7-01ecf565de81.png)

3. In the **New** dashboard, in the search bar, type **functions**

4. In the **New** dashboard, in the search bar tap the **[Enter]** key

![Marketplace Search Functions](https://user-images.githubusercontent.com/13558917/64928584-1d393000-d7cf-11e9-852d-fad28d656ae3.png)

5. On the **Marketplace** search results, click **Function App**

![Function App](https://user-images.githubusercontent.com/13558917/64928586-1e6a5d00-d7cf-11e9-9334-08eabee77898.png)

6. On the **Marketplace > Function App** window, select **Create** 

![Create Functions App](https://user-images.githubusercontent.com/13558917/64928581-1ad6d600-d7cf-11e9-9805-829a665e5d88.png)

7. On the **Function App Create** page, enter the following information:

- **App name**: XamarinAzureChallenge-[Your Name]
    - Note: The app name must be unique because it is used for the Azure Functions Url. This is why we'll append our name.
- **Subscription**: [Select your Azure Subscription]
- **Resource Group**:
    - [x] **Create new**
    - XamarinAzureChallenge
- **Hosting Plan**: Consumption Plan
- **Location**: [Select the Azure Datacenter closest to you]
- **Runtime Stack**: .NET Core
- **Storage**:
    - [x] **Create new**
    - xamarinazurechallenge[Your Name]
        - Note: The Storage name must be unique, which is why we append our name

7. On the **Function App Create** page, Click **Create**

![Enter Functions App Data](https://user-images.githubusercontent.com/13558917/64928583-1ca09980-d7cf-11e9-83ad-df824d193d66.png)

8. On the **Azure Portal**, at the top of the page, tap the notifications button which is shaped like a bell

9. In the **Notifications** window, ensure it says **Deployment in progress...**

![Deployment in progress](https://user-images.githubusercontent.com/13558917/64928694-ce4cc400-d7e9-11e9-8b87-c57a5695d6b2.png)

10. Stand by until the deployment has suceeded

~[Deployment Succeeded](https://user-images.githubusercontent.com/13558917/64928721-3b605980-d7ea-11e9-9996-89f7d0ff8ef1.png)

11. Go to Visual Studio and click on the Solution Explorer and select XamarinAzureChallenge.Functions project.

![publish](https://user-images.githubusercontent.com/13558917/57552330-690b3280-7320-11e9-97e8-18531a238b5b.png)

12. On the project, right-click in **Publish**

![start](https://user-images.githubusercontent.com/13558917/57552303-53960880-7320-11e9-958d-e44cf122bf6a.png)

13. Select existing resource -> Publish

![portal-publish](https://user-images.githubusercontent.com/13558917/57552081-96a3ac00-731f-11e9-91ae-6f72afecdf0a.png)

14. In the App Service window, select the Azure Function that you created earlier, and click **OK**.

![portal-publish-2](https://user-images.githubusercontent.com/13558917/57552471-dd45d600-7320-11e9-9011-dabe786e8dcb.png)

Visual Studio will publish your Azure Function. This action will take a few minutes.

### 2c. Use Azure CLI to create and publish your Azure Function. 

> As a prerequisite, you must have installed [Azure Core Tools version 2.x](https://docs.microsoft.com/azure/azure-functions/functions-run-local?WT.mc_id=xamarinazurechallenge-github-bramin#v2) and [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?WT.mc_id=xamarinazurechallenge-github-bramin)) or [Azure Cloud Shell](https://shell.azure.com/bash?WT.mc_id=xamarinazurechallenge-github-bramin).

1. Login into Azure CLI

```bash
az login
```

2. Create a resource group.

```bash
az group create --name XamarinAzureChallengeRG --location westeurope
```

If you have more than one subscription you will need to especify the subscription where the resource groups will be created with ``--subscription.`` 

3. Create an Azure storage account

```bash
az storage account create --name xamazurechallengestore1 --location westeurope --resource-group XamarinAzureChallengeRG2 --sku Standard_LRS --subscription bc6ccc1f-0744-4645-99f4-52b017e3b9ba
```

4. Use the following command to navigate to the project folder `XamarinAzureChallenge.Functions` project folder.

```bash
cd MyPath\src\XamarinAzureChallenge\XamarinAzureChallenge.Functions
```

5. Create a function app

```bash
az functionapp create --resource-group XamarinAzureChallengeRG2 --consumption-plan-location westeurope --name XamarinAzureChallengeFunctions --storage-account  xamazurechallengestore1 --runtime dotnet --subscription bc6ccc1f-0744-4645-99f4-52b017e3b9ba
```

6.  Use this command to deploy the project to Azure.


```bash
func azure functionapp publish XamarinAzureChallengeFunctions
```

## Task 2: Configuring the Xamarin App

### Configure your deploymemt

After deploy and publish the Azure Function, you are ready to configure the Xamarin app with your Azure Function endpoint.

1. Go the Azure Portal and navigate to your Azure Function App.

2. Open the list of Functions and select SubmitChallengeFunction. On the right panel, go to Get function URL.

![AFEndpoint](https://user-images.githubusercontent.com/13558917/57551436-e97c6400-731d-11e9-8ac7-eb8ae884c69e.png)

3. Copy the URL.

![AFEndpoint2](https://user-images.githubusercontent.com/13558917/57551471-f8631680-731d-11e9-9e39-8b7f50f56534.png)

4. Open the solution *XamarinAzureChallenge.sln* and go to *UserDetailViewModel* class and paste the url in *Endpoint* variable:

![ViewModel](https://blobstoragesampleapp.blob.core.windows.net/photos/BaseViewModel.png)


## Task 3: Goal of this challenge

As you know, this code contains errors. Please find them and fix them to pass this challenge!

**Click [here](/doc/solution.md) to get the solution.**

## Task 4: Submit your information through Xamarin Application 

The next step is to run the Xamarin Application and fill the form with your information. If you followed all the steps, your personal information will be sent to the Azure Function. The Azure Function will send to our internal API the data to participate in the challenge. 

You can run the app in local using an emulator. You can find the instructions [here](https://docs.microsoft.com/xamarin/android/deploy-test/debugging/debug-on-emulator?tabs=windows&WT.mc_id=xamarinazurechallenge-github-bramin).

In addition, you can run the app in a physical device. To setting up and configure your device you can follow [these instrucions](https://docs.microsoft.com/xamarin/android/deploy-test/debugging/debug-on-device?tabs=windows&WT.mc_id=xamarinazurechallenge-github-bramin)


## Next Steps

Please, read the Terms and Conditions of this challenge to know more about the next steps. 

## Report an issue

If you found an issue with this challenge, please open an issue in GitHub. 

## Additional Resources

If you are interested in learning more about this topic, you can refer to the following resources:

* [Azure Function Documentation](https://docs.microsoft.com/azure/azure-functions?WT.mc_id=xamarinazurechallenge-github-bramin)
* [Xamarin Documentation](https://docs.microsoft.com/xamarin?WT.mc_id=xamarinazurechallenge-github-bramin)
* [Azure Samples + Xamarin](https://github.com/Azure-Samples?utf8=%E2%9C%93&q=Xamarin&type=&language=&WT.mc_id=xamarinazurechallenge-github-bramin)
