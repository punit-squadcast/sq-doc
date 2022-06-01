# CircleCI

Integrate CircleCI to perform actions directly from Squadcast

### CircleCI Actions <a href="#circleci-actions" id="circleci-actions"></a>

[CircleCI](https://circleci.com/) is a modern continuous integration and continuous delivery (CI/CD) platform. CircleCI automates build, test, and deployment of software.

Squadcast’s **Extension** with CircleCI enables you to rebuild projects from within the Squadcast platform.

This is primarily helpful in a situation where you want to quickly mitigate a _customer experience_ issue by rolling back to an older successful build.

#### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* Only the Account Owner and Users with the `Manage Extensions` permission will be able to enable, disable and manage Extensions in Squadcast

#### Enabling CircleCI Extension <a href="#enabling-circleci-extension" id="enabling-circleci-extension"></a>

**(1)** Navigate to **Settings** and select the **Extensions** tab from the left navigation sidebar

**(2)** Move over to the CircleCI extension and click on **Integrate**

**(3)** In your CircleCI dashboard, move over to **User Settings**

**(4)** Click on **Personal API Tokens** and then, **Create New Token** to create a new API token for Squadcast

**(5)** Use a meaningful name for the token like “Squadcast” or “Squadcast Incidents”. Click on **Add API Token** to save and view the API Token

**(6)** Copy the API Token shown in the CircleCI screen

**(7)** Paste the copied API Token in the Squadcast CircleCI extension screen and click on **Save** to enable your CircleCI integration

Your CircleCI integration is good to go and you will be able to perform CircleCI actions directly for any incident.

#### Using CircleCI Actions <a href="#using-circleci-actions" id="using-circleci-actions"></a>

Now that the CircleCI extension is enabled, follow the steps below to understand how to take CircleCI actions from within Squadcast.

**(1)** Navigate to the Incident Details page of an incident for which you want to take the CircleCI action. In this example, we’re choosing the incident below to demonstrate.

**(2)** Click on **Actions** to see a list of allowed/enabled actions for your Organization

**(3)** Select **CircleCI** from the list of allowed/enabled actions

**(4)** Click on **Rebuild** from the **Actions** to see a list of projects you can take this action on

**(5)** Click on a **Project** of your choice and the **Build** you want to rollback to

**(6)** Click the **Rebuild** button to trigger the build again and you can see the link to the CircleCI build in the resulting screen

You will also be able to see the actions performed in the **Incident Activity Timeline** on the right.

The link will take you straight to the CircleCI **Jobs View** screen showing the result of the triggered build action.
