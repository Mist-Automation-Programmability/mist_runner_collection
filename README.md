# mist_runner_collection
This collection provides a number of Mist automation tasks that can be performed with Postman Runner.  Each folder represents a task.  The details can be found under the description of each subfolder.

Current Tasks include:
- Mist Site Creation
- Mist Device Naming

The details for each can be found under the details of that folder.

Note: Site creation requires a google maps API key.

## Installation:
There is only really one file needed, the `Mist_Runner_collection.json` from the `Postman Collection` folder
You can download this file directly, or clone the git repo which includes some example CSV files.

### Clone Repo
`git clone https://github.com/Mist-Automation-Programmability/mist_runner_collection`

## Import into Postman
1. From Postman, click the "import" button.
2. Select file and click `Upload Files`
3. Browse and select the `Mist_Runner_collection.json` that you downloaded, click open


## Dealing with Variables
These collection use a tremendous number of environmental variables to make things work.
Typically, each folder containing and automation will define which variables it needs.  These can be set multiple ways.
Current required variables are:
- apitoken
- org_id

### Environmental Variables
The preferred method for setting these variables is through an environment.  Most of the collection will require an `{{apitoken}}` and an `{{org_id}}` to be defined.  You can create a new Environment and define/set these variables.

### Collection Variables
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
- Check the box next to "Save Responses"
- Feel free to adjust other options as you see fit.
- Optionally, you can alter the number of iterations if you don't want to run the whole thing at once.
- Click `Run Mist Runner`

## Verifying the Results:
Since this is postman and more sophisticated autmation tools, you are reliant on the output to verify that these actions have been completed successfully.
(Update) I have attempted to do some validation of results with the testing features.  During Runner execution you should see test failing if some assumptions aren't met.

### Inherited Works
Most of the Mist API calls come from the Thomas Munzer Mist Postman collection.  They have been modified to with additional tests and scripts.