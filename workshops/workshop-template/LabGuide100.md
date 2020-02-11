![](images/lab100/100logo.png)

Updated: February 10, 2020

## Introduction

This is a workshop that will walk you through how to successfully create a fully functional web application using VBCS. Though the web application that we will be creating is relatively simple, the lab will walk you through many of the common features of VBCS that Developers often use. Specifically, the workshop will cover: 

- Drag-and-Drop UI Design
- REST API configuration 
- Action Chain configuration
- Data Flow within VBCS

**_To log issues_**, click here to go to the [github oracle](https://github.com/oracle/learning-library/issues/new) repository issue submission form.

## Objectives
- For this workshop, we will create a Web Application that lists out Countries and information specific to a certain country when a country row is clicked on, as shown below:

- The following actions need to be done for this project:
    - Build a Front-End 
    - Configure REST API connections
    - Implement logic using Action Chains
    - Manage Data Flow through a combination of Variables, Event Listeners and Action Chains

## Required Artifacts
- The following lab requires an Oracle Cloud account as well as an instance of VBCS already created

## Create the Web Application Project

### **STEP 1**: Create a New Project

- On the main menu of VBCS, click the `+ New Application` button

- Enter a name for the application, then click `Finish`

- Now that we've successfully created a new Project, we can begin to create the actual web application itself. Click on the `Desktop icon` on the left side below the Phone icon. For the purposes of this workshop, we will be creating a Web application, **NOT** a Mobile application

- Enter a name for the web application, then click `Create`

- With the web application now created, expand the `Flows` hierarchy. Right click the `main-start` file and rename it to `landing`. This will be the landing page for our app (alternatively, think of it as an index.html file for any other app you may have built)

- The wep application has been successfully set up at this point. Before we begin building the Front End UI, let's set up our REST connection.

### **STEP 2**: Create the REST API Connection

With our web application structure set up, we can now set up our REST connection. Specifically, our app will be consuming information from this link: https://restcountries.eu/#api-endpoints-all. Essentially, what we need are two endpoints from this server: an endpoint that returns **all** countries' information, and an endpoint that returns information for a **specific** country.

Setting up the GET endpoint for all countries:

- Click on the `Service Connections` tab on the left, and hit `+ Service Connection`
- Click `Define by Endpoint`
- Enter `https://restcountries.eu/rest/v2/all` into the URL input, then click `Next`
- Rename the `Service Name` to `Countries`
- In the `Test` tab, click `Send` and verify that the status code returned is 200
- Click `Copy to Response Body`, ignoring any warning messages that may pop up
- Click `Create`

Setting up the GET endpoint for a specific country:
- Follow the same steps above, but instead for the URL input, enter: `/name/{countryName}`
- In the `Action Hint` selection box, change the value from `Get Many` to `Get One`, then verify that the connection has been successfully set up with the string `Afghanistan` (similar to above, you should get a 200 code)
- Click `Create`




- If you see a message requesting that you **Set Replication Policy** as is shown below, click on the message. If the message is not displayed, your replicatin policy has already been set and you can continue to the next step by clicking on the **Dashboard** icon in the top right corner of the page.

    ![](images/100/Picture-02.png)

- Care must be taking when setting your replication policy, because it cannot be changed. With Trial accounts, the first option available will generatlly set the replication policy sufficient for this workshop, so we will take the Default, and click on the **Set** button. 

    ![](images/100/Picture-03.png)

- Click on the **Dashboard** button

    ![](images/100/Picture-04.png)

### **STEP 3**: Login to Developer Cloud Service

Oracle Developer Cloud Service provides a complete development platform that streamlines team development processes and automates software delivery. The integrated platform includes an issue tracking system, agile development dashboards, code versioning and review platform, continuous integration and delivery automation, as well as team collaboration features such as wikis and live activity stream. With a rich web based dashboard and integration with popular development tools, Oracle Developer Cloud Service helps deliver better applications faster.

- From the Cloud UI dashboard click on the **Developer** service. In our example, the Developer Cloud Service is named **developer99019**.

    ![](images/100/Picture100-6.png)

- The Service Details page gives you a quick glance of the service status overview.

    ![](images/100/Picture100-7.png)

- Click **Open Service Console** for the Oracle Developer Cloud Service. The Service Console will then list all projects for which you are currently a member.

    ![](images/100/Picture100-7.5.png)

### **STEP 4**: Create Developer Cloud Service Project

- Click **New Project** to start the project create wizard.

    ![](images/100/Picture100-8.png)

- On Details screen enter the following data and click on **Next**.

    **Name:** `Twitter Feed Marketing Project`

    **Description:** `Project to gather and analyze twitter data`

    **Note:** A Private project will only be seen by you. A Shared project will be seen by all Developer Cloud users. In either case, users need to be added to a project in order to interact with the project.

    ![](images/100/Picture100-9.png)

- Leave default template set to **Empty Project** and click **Next**

    ![](images/100/Picture100-10.png)

- Select your **Wiki Markup** preference to **MARKDOWN** and click **Finish**.

    ![](images/100/Picture100-11.png)

- The Project Creation will take about 1 minute.

    ![](images/100/Picture100-12.png)

- You now have a new project, in which you can manage your software development.

    ![](images/100/Picture100-13.png)



# Create Product Issues

## Create Issues for Twitter Feed Microservice

### **STEP 5**: Create Issue for the initial GIT Repository Creation

In this step you are still assuming the identity of the Project Manager, ***Lisa Jones***.

![](images/lisa.png)

- Click **Issues** on left hand navigation panel to display the Track Issues page.

    ![](images/100/Picture100-16.png)

- Click **New Issue**. Enter the following data in the New Issue page and click **Create Issue**.

    **Note:** Throughout the lab you will assign your own account as the “physical” owner of the issue, but for the sake of this workshop, **Bala Gupta** will be the “logical” owner of the following issues.

    ![](images/bala.png)

    **Summary:**
    `Create Initial GIT Repository for Twitter Feed Service`

    **Description:**
    `Create Initial GIT Repository for Twitter Feed Service`

    **Type:** `Task`

    **Owner:** `Select your account provided in the dropdown [Logical Owner: Bala Gupta]`

    **Story Points:** `1`

    Note: Story point is an arbitrary measure used by Scrum teams. They are used to measure the effort required to implement a story. This [Site](https://agilefaq.wordpress.com/2007/11/13/what-is-a-story-point/) will provide more information. 

    ![](images/100/Picture100-17.png)

### **STEP 6**: Create Issue for Update Twitter Credentials

- Click **New Issue**. Enter the following data in the New Issue page and click **Create Issue**.

    ![](images/bala.png)

    **Summary:** `Create Filter on Twitter Feed`

    **Description:** `Create Filter to allow user to supply text to reduce the amount of data returned by the Twitter feed`

    **Type:** `Feature`

    **Owner:** `Select your account provided in the dropdown [Logical Owner: Bala Gupta]`

    **Story Points:** `2`

    ![](images/100/Picture100-18.png)

### **STEP 7**: Create Issue for initial GIT Repository creation

- Click **New Issue**. Enter the following data in the New Issue page and click **Create Issue**. Note: The next two issues will logically be owned by John Dunbar.

    ![](images/john.png)

    **Summary:** `Create Initial GIT Repository for Twitter Feed Marketing UI`

    **Description:** `Create Initial GIT Repository for Twitter Feed Marketing UI`

    **Type:** `Task`

    **Owner:** `Select your account provided in the dropdown [Logical Owner: John Dunbar]`

    **Story Points:** `1`

    ![](images/100/Picture100-19.png)

### **STEP 8**: Create Issue for Displaying Twitter Feed

- Click **New Issue**. Enter the following data in the New Issue page and click **Create Issue**.

    ![](images/john.png)

    **Summary:** `Display Twitter Feed in Table Format`

    **Description:** `Display Twitter Feed in Table Format`

    **Type:** `Feature`

    **Owner:** `Select account provided in the dropdown [Logical Owner: John Dunbar]`

    **Story Points:** `2`

    ![](images/100/Picture100-20.png)

- Click the back arrow ![](images/100/Picture100-21.png) on the **left side** of the window, or click on the **Issues** menu option to view all newly created issues.

    ![](images/100/Picture100-22.png)


