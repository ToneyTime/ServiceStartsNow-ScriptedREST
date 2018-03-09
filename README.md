# ServiceStartsNow - Import Sets supercharged with Scripted REST

Welcome, this repo hosts the ServiceNow code for my example of Scripted REST being utilized along side Import Sets in the ServiceNow platform.
This was created for sharing during the **2018 ServiceNow Knowledge Conference - CreatorCon CCB0118** session.

We will outline installation and usage steps. You can also find information and walk-through on my blog [ServiceStartsNow.com](https://servicestartsnow.com/category/project/scripted-rest-in-import-sets/)

This code should be compatible with Istanbul and above versions of ServiceNow.

## Download the Repository XML and import to your instance
From this Github, please download the .xml file or zip file to your local device.

From within your ServiceNow instance, navigate to **Retrieved Update Sets**, open the list view and select 
**Import Update Set from XML** from the UI Action at the bottom of the page.

Finally, preview and commit. You may see error messages on some releases such as Istanbul, you can select "Accept" to proceed and commit. This will function correctly within Istanbul and above releases of ServiceNow.

Once this is done, you may want to refresh your browser page. Please activate **SvcStartsNow Rest Import** as your current application from the developer application scope.

## Configure app for your instance
First, navigate to **Service Start Now - REST API Example > Administration > Test REST: URL Variable**.
Modify the two records so that Test Value = the company name of your instance.

For example, if your instance URL is https://CompanyDev.service-now.com/, you will enter **CompanyDev** into the Value of both records.

## Create a local test account
Next, you will need to create a local account to be used as a Service Account during our testing

Create a new User. Name it whatever you like and be sure to give it a password.
Once created, grant it the following roles:
* rest_service
* x_8488_ssn_rest.import_role

Finally, you will select from the left side menu **Service Starts Now - REST API Example > Administration > Test REST Message**.
Open the record listed and then find **Basic auth profile**. Open that record and enter in the username and password for the account you had just created.

If this entire record is read only, you may need to first ensure that **SvcStartsNow Rest Import** is your current application.

# Lets Test It!
Now we will confirm you've installed and setup everything properly. Note that this test will create/update a single user account so be careful to do this only in subproduction instances.

Navigate from the left side menu to **Service Starts Now - REST API Example > Administration > Test REST Message**.
Open the record and from the Related List, select either of the Test messages.

Scroll down to the bottom and select the UI Action for Test.
The test should run and your response should contain **{"http_status":"201","status_message":"User payload accepted and processed. Profile created for 123"}**

Finally, open your user table list of records and look for records updated on today. You should find the new record with basic fields representing that the integration test worked succesfully.
