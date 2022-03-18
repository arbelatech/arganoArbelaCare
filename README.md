# arganoArbelaCare
Power Platform based Solution to Check-in on your employees and provide the support they need during unfortunate events.

## Installation Instructions

### Prerequisites
* Have access to an Office 365 User with a Power Apps license
* Have system admin access to a target power apps environment where the solution will be deployed
* Download the Managed Solution file ""
* Download all Sample Data files (.xlsx) - If any.

### Download and Pack the Solution
1. Download from the solution from GitHub
2. Use the Power Apps CLI tool to pack the unpacked solution within the "source" directory. 
3. Use the produced Solution Zip file to import to your target environment. 

### Install Solution
1. Go to https://make.powerapps.com/, select your target environment, and open "Solutions"
	* If you do not have a Power Apps license, sign up for the Power Apps Community Plan
	* If you do not have an environment, create one through the Power Platform Admin Center
2. From the Solutions screen, select "Import" in the Command Bar
3. Within the Import Solution dialog, select "Choose File" and select the "Unmanaged Solution file" file downloaded previously
4. Proceed through the dialog window with defaults selected and initiate the solution import process
5. When complete, there may be warnings noted, but this is ok as long as the Solution has been installed
6. Set any unset environment variables as directed below.
7. Import Data using the arganoArbela Admin App.
8. Direct People in Support to download and use arganoArbela Cares canvas app. 

### Environment Variables
The following environment variables need to be set. Some values may not be available until after the resources are created in the target environment. Leave these values blank on initial import. Once import is complete retreive and set these values. 
<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Example</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
		<tr>
            <td>Environment URL</td>
            <td>https://orgXXXX.crm.dynamics.com/</td>
            <td>URL of the target environment (ex: https://orgXXXX.crm.dynamics.com/). It can be found in the admin center</td>
        </tr>
		<tr>
            <td>arganoArbela Cares Admin App Id</td>
            <td>00000000-0000-0000-0000-000000000000</td>
            <td>GUID of arganoArbela Cares Admin App (Model-Driven). Leave blank for first import. Once the solution is installed, find this value in the details pane.</td>
        </tr>
		<tr>
			<td>arganoArbela Cares App Id</td>
            <td>00000000-0000-0000-0000-000000000000</td>
            <td>GUID of arganoArbela Cares App (Canvas). Leave blank for first import. Once the solution is installed, find this value in the details pane.</td>
		</tr>
        <tr>
            <td>Financial Requests Contacts</td>
            <td>name@email.com; name2@email.com;</td>
            <td>Comma separated list of people who should be notified on creation of Finanical Requests</td>
        </tr>
		 <tr>
            <td>ArganoArbelaCare Dashboard</td>
            <td>
				{
    				"group": {
        				"id": "00000000-0000-0000-0000-000000000000",
        				"name": "ArganoArbela Check In and Care"
    				},
    				"component": {
						"id": "00000000-0000-0000-0000-000000000000",
						"name": "ArganoArbelaCare",
						"type": "Report",
						"embedUrl": "https://app.powerbi.com/reportEmbed"
    				}
				}
			</td>
            <td>JSON representation of Power BI Report and Dashboard. Leave Blank on Import. (https://docs.microsoft.com/en-us/powerapps/maker/model-driven-apps/create-edit-powerbi-embedded-page#create-power-bi-embedded-page-with-an-environment-variable)</td>
        </tr>
    </tbody>
</table>

### Admin App Set Up
1. Confirm that all environment variables are set. 
2. Assign Security Roles as appropriate. Emergency Contacts and users of the Admin App should be assigned the arganoArbela Cares Admin Security Role. People in Support should receive the People in Support Security Role. 
3. Use the arganoArbela Cares Admin app to import data. 
4. Add data in the following order: Emergency Contacts, People in Support, then Available Options. 

### Person in Support Mobile App Set Up
1. Download the Power Apps mobile app.
2. Sign in
3. Go to All apps and search for the arganoArbela Care App.
4. Select the app to open the details page.
5. Favorite the app and Create a Shortcut for best experience.
