[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?hide_repo_select=true&ref=main&repo=526682400)

# Python HTTP API with GitHub Codespaces and Copilot

_Run a Python API in this ready-to-use-repository in minutes_

By opening this template respository in Codespaces, you can quickly get hands-on with a Python web app that serves an HTTP API. You'll get to focus on working with the project instead of setup and configuration. And then you'll make changes to the code using [GitHub Copilot](https://copilot.github.com/), a new AI-powered code completion tool that helps you write code faster.

## 🚀 Quick start
1. [Follow the steps](#--try-it-out) to setup your Codespace and run the app.
1. [Make changes to the application](#make-changes-using-copilot) using [GitHub Copilot](https://copilot.github.com/) to make changes to the code.
1. Take the challenge and deploy your app to Azure.

🤔 Curious? Watch the following video where we explain all the details:

[![Python development environment with Codespaces](https://img.youtube.com/vi/_i9Pywj3rSg/0.jpg)](https://youtu.be/_i9Pywj3rSg "Python Development environment with Codespaces")


<details>
   <summary><strong>Learn more about APIs</strong></summary>

   An API (Application Programming Interface) describes a way for two computers to interact.
   An HTTP API allows an Internet-connected computer to send an HTTP request to another Internet-connected computer
    and receive a response. For example, my computer could send a request to
   `http://a-weather-website-api.com/api/city=Los+Angeles` and receive back data like `{"high": 72, "low": 66}`.

   HTTP APIs often provide either data or functionality that's unique to a service, like the example API for the weather website. A weather website could provide additional API endpoints for other weather-related functionality, like upcoming forecasts or historical data. Any website can decide to offer an API if it thinks it has helpful functionality to share
   with other computers. In this project, you'll run an HTTP API that generates a random token.
</details>

This template is also ready to be used with [Codespaces](https://github.com/features/codespaces), a developer environment running in the cloud with [Visual Studio Code](https://visualstudio.microsoft.com/?WT.mc_id=academic-77460-alfredodeza).

<details>
   <summary><b>🎥 Watch the video tutorial to learn more about Codespaces</b></summary>

   [![Codespaces Tutorial](https://img.youtube.com/vi/ozuDPmcC1io/0.jpg)](https://aka.ms/CodespacesVideoTutorial "Codespaces Tutorial")
</details>

## For students and developers

Using Codespaces, you get [Visual Studio Code](https://visualstudio.microsoft.com/?WT.mc_id=academic-77460-alfredodeza) in the cloud, using a ["development container"](https://containers.dev/). Like a locally running version of [Visual Studio Code](https://visualstudio.microsoft.com/?WT.mc_id=academic-77460-alfredodeza), the cloud version also allows you to install extensions and use a terminal.

You can also configure your development container to run a specific runtime and have it boot up with your favorite extensions.

Here are the key files and folders that make it happen:

- [webapp/](./.webapp): The HTTP API code, built with the FastAPI framework.
- [.devcontainer/Dockerfile](./.devcontainer/Dockerfile): Configuration file used by Codespaces to determine operating system and other details.
- [.devcontainer/devcontainer.json](./.devcontainer/devcontainer.json), A configuration file used by Codespaces to configure [Visual Studio Code](https://visualstudio.microsoft.com/?WT.mc_id=academic-77460-alfredodeza) settings, such as the enabling of additional extensions.

## 🧐 Use Codespaces

Try out this template repository using Codespaces following these steps:

1. Create a repository from this template. Use this [create repo link](https://github.com/microsoft/codespaces-project-template-py/generate). You can make the repository private or public, up to you.
1. Before creating the codespace, enable GitHub Copilot for your account! If it is not enabled, take a look on [Make changes using Copilot](#make-changes-using-copilot)
1. Navigate to the main page of the newly created repository.
1. Under the repository name, use the Code drop-down menu, and in the Codespaces tab, select "Create Codespace on main".
   ![Create Codespace](https://docs.github.com/assets/cb-138303/images/help/codespaces/new-codespace-button.png)
1. Wait as Github initializes the codespace:
   ![Creating Codespace](https://github.com/microsoft/codespaces-teaching-template-py/raw/main/images/Codespace_build.png)

### Inspect your Codespaces environment

What you have at this point is a pre-configured environment where all the runtimes and libraries you need are already installed - a zero config experience.

## Running the App

This Python application is using FastAPI, a powerful web framework that self-documents its API endpoints. The API has only one endpoint that generates a unique pseudo-random string that can be used as a token.


![Running FastAPI](./images/api-running.png)


<details>
<summary><b>Run FastAPI inside the Codespace</b></summary>

The API included in this template repository has a single endpoint that generates a token. Get it up and running using the following steps:

1. Open up a terminal window by opening up the command palette (Ctrl-Shift-P or Cmd-Shift-P) and then select "Open new Terminal" command.
1. Run `uvicorn` in the console to start up your API application:

    ```console
    uvicorn --host 0.0.0.0 webapp.main:app --reload
    ```

    You should see output similar to:

    ```output
    INFO:     Uvicorn running on http://127.0.0.1:8000 (Press CTRL+C to quit)
    INFO:     Started reloader process [28720]
    INFO:     Started server process [28722]
    INFO:     Waiting for application startup.
    INFO:     Application startup complete.
    ```

    You'll get a pop-up that says your application is available at port 8000. Click the button to open it in the browser.
1. Once the site loads, click on the _Try it Out_ button or append `/docs` to the URL in the address bar. The automatically generated API documentation should load and look like this:

   ![OpenAPI docs](./images/fast-api.png)

1. Finally, try to interact with the API by sending a request using the self-documented page. Click on the _POST_ button and then on the _Try it Out_ button:

   ![Try a POST request](./images/try-it-out.png)

🔒 Do you see the lock next to the URL of the website in the browser? That indicates the website is being served over a secure HTTPS connection which encrypts the HTTP responses. That's very important whenever an API can receive sensitive data or respond with sensitive data (like a password).

</details>

## Customize the Codespace

You can change your environment and the text editor so that the next time you create (or rebuild) the environment, everything will be set automatically. Let's go through two different challenges that you are likely to want to do:

1. Changing the Python version
1. Adding or modifying a pre-installed editor extension


<details>

### Step 1: Change the Python environment

Let's say you want to change which version of Python is installed. This is something you can control.

Open [.devcontainer/devcontainer.json](./.devcontainer/devcontainer.json) and replace the following section:

```json
"VARIANT": "3.8-bullseye"
```

with the following instruction:

```json
"VARIANT": "3.9-bullseye"
```

This change instructs Codespaces to use Python 3.9 instead of 3.8.

If you make any configuration change in `devcontainer.json`, a box will appear after saving.

![Recreating Codespace](https://github.com/microsoft/codespaces-teaching-template-py/raw/main/images/Codespace_rebuild.png)

Click on rebuild. Wait for your Codespace to rebuild the VS Code environment.

### Step 2: Add an extension

Your environment comes with pre-installed extensions. You can change which extensions your Codespaces environment starts with. Here's how:

1. Open file [.devcontainer/devcontainer.json](./.devcontainer/devcontainer.json) and locate the following JSON element **extensions**:

   ```json
   "extensions": [
    "ms-python.python",
    "ms-python.vscode-pylance"
   ]
   ```

1. Add _"ms-python.black-formatter"_ to the list of extensions. It should end up looking like the following:

   ```json
   "extensions": [
    "ms-python.python",
    "ms-python.vscode-pylance",
    "ms-python.black-formatter"
   ]
   ```

   That string is the unique identifier of [Black Formatter](https://marketplace.visualstudio.com/items?itemName=ms-python.black-formatter&WT.mc_id=academic-77460-alfredodeza), a popular extension for formatting Python code according to best practices. Adding the _"ms-python.black-formatter"_ identifier to the list lets Codespaces know that this extension should be pre-installed upon startup.

   Reminder: When you change any configuration in the JSON file, a box will appear after saving.

   ![Recreating Codespace](https://github.com/microsoft/codespaces-teaching-template-py/raw/main/images/Codespace_rebuild.png)

   Click on rebuild. Wait for your Codespace to rebuild the VS Code environment.

To find the unique identifier of an extension:

- Navigate to the extension's web page, for example [https://marketplace.visualstudio.com/items?itemName=ms-python.black-formatter](https://marketplace.visualstudio.com/items?itemName=ms-python.black-formatter&WT.mc_id=academic-77460-alfredodeza)
- Locate the *Unique Identifier* field under **More info** section on your right side.

</details>


## Make changes using Copilot

Let's go through some steps to make changes to the code using Copilot. This is a great way to learn how to use Copilot and get useful suggestions for faster development. Note that these are suggested solutions, and we advise that you review them to ensure they are applicable to your code.

This Codespaces repository has the Copilot extension enabled already. Make sure your account has access to it. If you don't have access, you can [request it](https://github.com/login?return_to=%2fgithub-copilot%2fsignup) and then install the extension [here](https://aka.ms/get-copilot). If you are a student, you can get Copilot for free [following these instructions](https://techcommunity.microsoft.com/t5/educator-developer-blog/step-by-step-setting-up-github-student-and-github-copilot-as-an/ba-p/3736279?WT.mc_id=academic-0000-alfredodeza).

To ensure that Copilot is running correctly, please follow these steps:

1. Verify if Copilot is activated by navigating to the extension tab in your codespace and checking the status.
1. If the status is inactive, recreate the codespace, and enable the extension to ensure that it is activated.

🤔 Curious? Watch the following video where we explain all the details:

[![Assisted AI Coding with GitHub Copilot](https://img.youtube.com/vi/9c7SSHbzD80/0.jpg)](https://youtu.be/9c7SSHbzD80 "Assisted AI Coding with GitHub Copilot")

<details>
<summary><b>Use Copilot</b></summary>

### Step 1: Change the HTML to make it interactive
Open the [index.html file](./webapp/static/index.html) and delete the following line:

```html
<button onclick="window.location.href='/docs'" type="button" class="btn btn-info">Try it out</button>
```

Now add a comment so that Copilot can generate code for you:

```html
<!-- create an interactive form with text input and button, and add event listener to button to send POST request to /generate endpoint and display response in a div with id "result" -->
```
This should be enough for Copilot to generate code for you after you press `Enter` (or `Return`). 
If not, use `Ctrl+Enter` to give multiple suggestions, choose one that fits better to the code below.
Remember, it is possible that copilot will not generate the exact snippet! In this case, type or overwrite the suggestion for the code below. 
The generated code should look like this:

```html
              <form id="form">
                <input type="text" id="input" placeholder="Enter text here">
                <button type="button" id="button" class="btn btn-info">Generate</button>
              </form>
              <div id="result"></div>
              <script>
                const button = document.getElementById('button');
                const form = document.getElementById('form');
                button.addEventListener('click', async (event) => {
                  event.preventDefault();
                  const input = document.getElementById('input').value;
                  const response = await fetch('/generate', {
                    method: 'POST',
                    headers: {
                      'Content-Type': 'application/json'
                    },
                    body: JSON.stringify({ text: input })
                  });
                  const data = await response.json();
                  const result = document.getElementById('result');
                  result.innerHTML = data.result;
                });
              </script>
```

Run the application and verify the form shows up.

### Step 2: Update the HTML to fix a bug
The generated code introduced a couple of issues. First, the button is not working. Second, the form is not using the right JSON key when submitting the text to the API endpoint. Let's fix that.

Change the body of the request to use the length key instead of text:

```javascript
body: JSON.stringify({ length: input })
```

Now, lets change the `innerHTML` to use the `token` key instead of `result`:

```javascript
result.innerHTML = data.token;
```

Run the application and verify the form is now working.

### Step 3: Change the form to use a dropdown
The form is currently accepting any text as input. Let's change it to use a dropdown instead. Add a comment so that Copilot can generate code for you. Delete the following line:

```html
<input type="text" id="input" placeholder="Enter text here">
```

And add the following comment so that Copilot can generate code for you:

```html
<!-- create an input with a drop down menu to select from the following values: 5, 10, 15, 20-->
```

The generated code should now look like this:

```html
<select id="input">
   <option value="5">5</option>
   <option value="10">10</option>
   <option value="15">15</option>
   <option value="20">20</option>
</select>
```

Run the application again to verify the dropdown is working.

### Step 4: Add a new API endpoint
Now let's add some new functionality to the API. Add a new endpoint to the API that accepts a text and returns a list of tokens. Add the following comment so that Copilot can generate a Pydantic model for you:

```python
# Create a Pydantic model that accepts a JSON body with a single field called "text", which is a string
```

The generated model should look like this:

```python
class Text(BaseModel):
    text: str
```

Next, add the following comment so that Copilot can add a new endpoint:

```python
# Create a FastAPI endpoint that accepts a POST request with a JSON body containing a single field called "text" and returns a checksum of the text
```

The generated code should look like this:

```python
@app.post('/checksum')
def checksum(body: Text):
    """
    Generate a checksum of the text. Example POST request body:

    {
        "text": "Hello World!"
    }
    """
    checksum = base64.b64encode(os.urandom(64))[:20].decode('utf-8')
    return {'checksum': checksum}
```

The generated code will cause the application to crash. This is because the `base64` and `os` modules are not imported. Add the following lines to the top of the file:

```python
import base64
```

Finally, verify the new endpoint is working by going to the `/docs` page and trying out the new endpoint.

Congratulations! You've used Copilot to not only generate code, but also do it in a way that is interactive and fun. You can now use Copilot to generate code for you in any of your projects, including writing documentation, generating models, and more! Even portions of this README were generated using Copilot suggestions 🧐

</details>

## 🚀 Next steps

Take this API application to the next level and deploy it to the cloud! For this learning challenge you'll use a FREE deployment option for Azure and GitHub Actions for the automation.

Before continuing, make sure you have an Azure account ready. Select any of the following:

- [Sign in to your Azure account](https://azure.microsoft.com/en-US/?WT.mc_id=academic-77460-alfredodeza)
- [Create a (no Credit Card required) Azure For Students account](https://azure.microsoft.com/free/students/?WT.mc_id=academic-77460-alfredodeza)
- [Create a new Azure account](https://azure.microsoft.com/en-US/?WT.mc_id=academic-77460-alfredodeza)

There are a few steps involved, so make sure you get everything right!

<details>
<summary><b>Create an Azure App Service</b></summary>

Now, you are going to set up automatic deployment of the application using Azure plus GitHub actions! However, you first need to configure some Azure services.

1. Open the [Azure Cloud Shell](https://shell.azure.com/?WT.mc_id=academic-77460-alfredodeza).
1. Use the Bash shell (not PowerShell!) for these steps.
1. If it says "You have no storage mounted", select a subscription in your account and click "Create storage". The Cloud Shell uses that storage resource to store data generated during your shell sessions.
1. Create a *Resource Group* which will group together the different Azure resources used for the app:
```
az group create --name demo-fastapi --location "East US"
```
1. You'll see a JSON response with details about the newly created resource, for this command and all the commands that follow.
1. Create the **FREE** *App Service Plan*:
```
az appservice plan create --name "demo-fastapi" --resource-group demo-fastapi --is-linux --sku FREE
```
1. Create a random identifier for a unique webapp name:
```
let "randomIdentifier=$RANDOM*$RANDOM"
```
1. Create the *Web App Service* with a placeholder container using the `randomIdentifier` variable from before:
```
az webapp create --name "demo-fastapi-$randomIdentifier" --resource-group demo-fastapi --plan demo-fastapi --runtime "PYTHON:3.9"
```
1. Head to the Azure portal [App Services list](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Web%2Fsites) and confirm that your newly created service is listed.

</details>


<details>
<summary><b>Create an Azure Service Principal</b></summary>

Next, create an Azure Service Principal, which is a special type of account that has permissions necessary to authenticate from GitHub to Azure:

1. Find the ID of your Azure Subscription [in the Azure portal](https://portal.azure.com/#view/Microsoft_Azure_Billing/SubscriptionsBlade?WT.mc_id=academic-77460-alfredodeza) or [by following this guide](https://learn.microsoft.com/azure/azure-portal/get-subscription-tenant-id?WT.mc_id=academic-77460-alfredodeza).
1. Create a Service Principal with a "contributor" role that is allowed to make changes to any resources in that subscription. Replace $AZURE_SUBSCRIPTION_ID with the ID you found in step 1 and run this command:

```
az ad sp create-for-rbac  --sdk-auth --name "github-deployer" --role contributor --scopes /subscriptions/$AZURE_SUBSCRIPTION_ID
```

1. Capture the output and add it as a [Github repository secret](/../../settings/secrets/actions/new) with the name `AZURE_CREDENTIALS`. (_If that link doesn't work, make sure you're reading this on your own copy of the repo, not the original template._)

</details>

<details>

<summary><b>Setup GitHub Actions</b></summary>

Now that you have all the Azure resources created, you need to update the GitHub Action workflow file with the name of your webapp.

1. Find your app name. It should look something like `demo-fastapi-97709018` but with a different random number at the end,
and you can find it in the Azure portal or the Cloud Shell commands.
2. Open the [.github/workflows/web_app.yml](/../../edit/main/.github/workflows/web_app.yml) file and update the value of `AZURE_WEBAPP_NAME` to your app name.
3. Commit and push the changes to the Github repository:

```
git add .github/workflows/web_app.yml
git commit -m "Updating workflow file"
git push
```

</details>

<details>
<summary><b>🏃 Deploy your app!</b></summary>

Before continuing, check the following:

1. You've created an Azure Service Principal and saved it as a [repository secret](/../../settings/secrets/) as `AZURE_CREDENTIALS`.
1. You've created an [App Service](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Web%2Fsites) with a valid name and the site is already available with the default static content.

To deploy:

1. Navigate to [repository actions](/../../actions/workflows/web_app.yml). (_If that link doesn't open the "Build and deploy Python app" workflow, make sure you're reading this on your own copy of the repo._)
3. Select _Run workflow_ and select the green button inside the pop-up to run the workflow.

**Deploying can take a couple of minutes**. Make sure you stream the logs in the Azure Cloud Shell to check the progress:

```
az webapp log tail --name $AZURE_WEBAPP_NAME --resource-group $AZURE_RESOURCE_GROUP
```

4. Once deployment is complete, visit your website at a URL like `http://demo-fastapi-97709018.azurewebsites.net/`,
where the random number is your unique random number. You can find the website URL in the Azure portal or in the deployment logs if you forgot the number.
5. 🎉 Celebrate a successful deployment! You now have a URL that you can share with classmates, friends, and family.

### Destroy resources when complete

You likely don't want to keep this particular website running forever in the cloud, so you should cleanup your Azure resources by destroying the resource group. You can do it in the Azure Cloud Shell by referencing the group name you created initially (`demo-fastapi` in the examples):

```
az group delete --name demo-fastapi
```

### Deployment Troubleshooting

When deploying, you might encounter errors or problems, either on the automation part of it (GitHub Actions) or on the deployment destination (Azure Web Apps).

You can check the logs of the Github Actions workflow by selecting the latest workflow from the _Actions_ tab. Find the first step that has a broken icon next to it, and expand that step to see what went wrong in it.

If running into trouble with the Azure deployment, check logs in the portal or use the following with the Azure CLI:

```
az webapp log tail --name $AZURE_WEBAPP_NAME --resource-group $AZURE_RESOURCE_GROUP
```

Update both variables to match your environment.


</details>

## Other Resources

- [FastAPI](https://fastapi.tiangolo.com/)
- [Codespaces](https://github.com/features/codespaces)
- [Use Dev containers locally](https://github.com/Microsoft/vscode-remote-try-python)

### 🔎 Found an issue or have an idea for improvement?
Help us make this template repository better by [letting us know and opening an issue!](/../../issues/new).
