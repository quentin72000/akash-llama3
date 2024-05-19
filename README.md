# akash-llama3
This repository contains a step-by-step tutorial for deploy Llama 3, a powerful text-to-text AI model on [Akash](https://akash.network/), the World's Premier Decentralized Compute Marketplace.

The Llama 3 comes two versions:
- **The 70B** (heavy version, 160+ GB disk space required, uses more ram, but results can be better)
- **The 8B version** (light version, 16GB+ disk space required)

Make sure you choose the right version **according to your needs**, you will need it when deploying the SDL file.

## Step 1 : Access to the model 
You must have access to the Llama-3 model to be able to use it. We will use Hugging Face for this.

To do this, you will need to create an account on [Hugging Face](https://huggingface.co/join).

You will then need to apply access to the model by accepting the Meta Privacy Policy. This is usually quick but must be done with cautions.
Go to the [Llama-3 70B](https://huggingface.co/meta-llama/Meta-Llama-3-70B-Instruct/tree/main) or [Llama-3 8B](https://huggingface.co/meta-llama/Meta-Llama-3-8B-Instruct/tree/main) page and fill the form to request access. No matter on which one you request, the form will give you access to both the 8B and 70B versions. 

> [!IMPORTANT]
> Make sure you enter credible information in the form, as the access is not automatic and may be denied if the information are not credible.

You can enter "None" in the "Affiliation" field.

Your request should be reviewed shortly and you will receive an email when your request is approved. You can complete the next steps while you wait for access.


## Step 2 : Prepare the SDL file
The SDL file is a template file that will be used to deploy the model on Akash. It contains all the informations required to deploy the model.

You can find the SDL file for the Llama-3 70B version [here](/deploy-70B.yaml) and the SDL file for the Llama-3 8B version [here](/deploy-8B.yaml). Download the file corresponding to the version you wish to deploy.

You will need to modify the file to add your Hugging Face API key. You can find your API key in your Hugging Face account settings -> Access Token -> New token (only read access is required).
Make sure you keep it in a safe place as you will need it to deploy the model. **This is your personal access token, do not share it**.

In the SDL file, replace `hf_yourtoken` with **your own access token** (access tokens start with "hf_").

Optionally, you can change `YOURCUSTOMAPIKEY` to a custom API key (similar to a password) that you will use to access the model. This is optional, you can leave the default value if you want. You can also remove `--api-key YOURCUSTOMAPIKEY` if you don't want to use an API key to access the model.

## Step 3 : Deploy the model
To deploy the model, you will need an Akash Wallet. If you don't have one, you can use [Keplr Wallet](https://www.keplr.app/) or [Leap Wallet](https://www.leapwallet.io/). Make sure to have some AKT in your wallet to pay for the deployment.

We will use the [Akash Console](https://console.akash.network/) to upload the SDL file you modified in the previous step. Alternatively, you can use the [Cloudmos App](https://deploy.cloudmos.io/).

Connect your wallet to the Akash Console using the top right button and go to the "Deployment" section. Click on "Create Deployment" and use "Upload SDL" and select the SDL file you have modified.

Name your deployment and click on "Create Deployment". You will be asked for a "Deployment Deposit". The **minimum deposit** is 5 AKT. Approve the transaction and wait for it to be confirmed.

Now, wait for bids to be placed on your deployment. You should shortly see several provider ready to accept your deployment, who will compete to offer you the best price. 

Select the one you want to accept and click on "Accept Bid". The deployment will begin and you will be able to access the model once the deployment is complete.

> [!WARNING]
> The deployment will take time to download the model, especially for the 70B version. Be patient and wait for the deployment to be completed.

## Step 4 : Access the model
Once the deployment is completed, you will be able to access the model. In the "Lease" tab of the deployment, you will find the URI address for your deployment. You can use this URI to access the model API.

**:tada: Congratulations, you have successfully deployed the Llama-3 model on Akash. You can now use it to generate, summarize, or event translate text and much more. :tada:**