# ServiceStartsNow - Import Sets supercharged with Scripted REST

Welcome, this repo hosts the ServiceNow code for my example of Scripted REST being utilized along side Import Sets in the ServiceNow platform.
This was created for sharing during the 2018 ServiceNow Knowledge Conference - CreatorCon CCB0118 session.

We will outline installation and usage steps. You can also find information and walk-through on my blog [ServiceStartsNow.com](https://servicestartsnow.com/category/project/scripted-rest-in-import-sets/)

This code should be compatible with Istanbul and above versions of ServiceNow.

## Download the Repository XML and import to your instance
From this Github, please download the .xml file or zip file to your local device.

From within your ServiceNow instance, navigate to Retrieved Update Sets, open the list view and select 
Import Update Set from XML from the UI Action at the bottom of the page.

Finally, preview and commit. You may see error messages on some releases such as Istanbul, you can select "Accept" to proceed and commit. This will function correctly within Istanbul and above releases of ServiceNow.

## Configure app for your instance
First, navigate to Service Start Now - REST API Example > Administration > Test REST: URL Variable.
Modify the two records so that Test Value = the company name of your instance.

For example, if your instance URL is https://CompanyDev.service-now.com/, you will enter CompanyDev into the Value of both records.

## Create a local test account
Next, you will need to create a local account to be used as a Service Account during our testing

Create a new User. Name it whatever you like and be sure to give it a password.
Once created, grant it the following roles:
