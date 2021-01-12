# mist_runner_collection
This collection provides a number of Mist automation tasks that can be performed with Postman Runner.  Each folder represents a task.  The details can be found under the description of each subfolder.

### Current Tasks include:
- Site Creation
- Site Creation with Settings
- Inventory Assignment
- Update Sites(Group):
  - Firmware Settings
  - Add Webhook to Sites
  - Generic Site Update (put in whatever site settings you want)
  - Delete Sites
- Update Devices (Group):
  - Device Naming
  - Device IP
  - Device Notes  

The details for each can be found under the details of each folder.

Note: Site creation requires a google maps API key currently.

## Installation:
There is only really one file needed, the `Mist_Runner_collection.json` from the `Postman Collection` folder
You can download this file directly, or clone the git repo which includes some example CSV files.

#### Clone Repo
`git clone https://github.com/Mist-Automation-Programmability/mist_runner_collection`

## Import into Postman
1. From Postman, click the "import" button.
2. Select file and click `Upload Files`
3. Browse and select the `Mist_Runner_collection.json` that you downloaded, click open

## Dealing with Variables
These collection use a tremendous number of environmental variables to make things work.
Typically, each folder containing and automation will define which variables it needs.  These can be set multiple ways.
Most commonly required variables are
- `{{apitoken}}`
- `{{org_id}}`

*Note* If you have variables defined in your environment that conflict with the variables used in your .csv or .json files, the ones used in your environment will take preference.  To reduce this, disable any variables in your environment that are not needed.

#### Environmental Variables
The preferred method for setting these variables is through an environment.  Most of the collection will require an `{{apitoken}}` and an `{{org_id}}` to be defined.  You can create a new Environment and define/set these variables.

#### Collection Variables
On the `Mist Runner Collection` you can click the the dots and select `Edit`.  On the `Variables` tab you can set either the `Initial Value` or the `Current Value` for the required Variables

## Creating CSV Files
In the `Examples` Folder, there are a number of example CSV files for the different Runners.  You can start with these, or create a new one.

## Running the Collection
In Postman, click the `Runner` button.  From here, browse down to the folder in the collection you want to perform.
Once you've browsed to here, you can select the options.
- Pick your environment if are using one for Variables.
- Next to `Data`, Pick the CSV File.
- Adjust the `Data File Type` option to match your upload.
- You should preview the results to make sure things look correct.
- Check the box next to `Save Responses`
- Uncheck the box `Keep Variable Values`
- Feel free to adjust other options as you see fit.
- Optionally, you can alter the number of iterations if you don't want to run the whole thing at once.
- Click `Run Mist Runner`

## Verifying the Results:
Since this is postman and more sophisticated autmation tools, you are reliant on the output to verify that these actions have been completed successfully.

(Update) I have attempted to do some validation of results with the testing features.  During Runner execution you should see test failing if some assumptions aren't met.  This is a work in progress.  If there are tests you would like to see, please open an issue.

## Update Site Actions:
Instead of requiring a CSV, there is a call called `getSites - Send And Download`.  This will download a .json file with all of the site data that you can iterate through.  This has not been tested with orgs with 1k+ sites.


### Inherited Works
Most of the Mist API calls come from the Thomas Munzer Mist Postman collection.  They have been modified to with additional tests and scripts.
