# EECS605Module7
EECS 605 Module 7

Overview
We will be creating and deploying a React app to Heroku that can do handwritten-digit recognition via the handwritten-digit API that we created in Module 6.

Objectives

Refactor a React app template to utilize the handwritten-digit API.
Deploy the React app to Heroku.


Step 1: React app preparation

Create a public GitHub repository dedicated storing the React app components. (If you do not have a GitHub account, create one https://docs.github.com/en/get-started/signing-up-for-github/signing-up-for-a-new-github-account)
Copy and paste everything in the "components" directory into the GitHub repository's root level. Make sure to copy and paste .gitignore file also - you can do this by:

If MacOS: cmd -> shift -> . will reveal the hidden files, including the .gitignore file.
If Windows: https://stackoverflow.com/questions/42173328/why-doesnt-gitignore-txt-file-show-its-name-in-windows10



Open up ./src/App.js file and replace <api-url> with your API from Module 6.
Push the changes to the GitHub repository.


Step 2: Heroku preparation and deploy the React app

Create a new Heroku app from the console https://dashboard.heroku.com/apps.
Choose "GitHub" as the deployment method and connect your GitHub account.
Find and connect the GitHub repository to Heroku by following the steps.
Once the repository is connected, deploy it by selecting "Deploy Branch".


Step 3: Enable CORS policy on the API

Go to the API Gateway console and go to the API console for your API.
Under "Resources", select "Actions" and select "Enable CORS".
Keep the default settings and select "Enable CORS and replace existing CORS headers".
Re-deploy the API.
Give about 2-5 minutes for the API Gateway to update the API configurations.


Customizing

Main resource: https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/file

You can start customizing your website from src/App.js, specifically at the bottom of the code where you will see the website components such as <div className="Input"> or <input type="file" onChange={handleChange} />.
"Choose File" button is being created by <input type="file" onChange={handleChange} />.
"Submit" button is being created by <button type="submit" disabled={buttonDisable}>{buttonText}</button>.
The image processing and upload is handled by <form onSubmit={handleSubmit}> ... </form>.
Output is being handled by <p>{outputFileData}</p>, where outputFileData is a global variable that is being updated by handleSubmit() function when the output is returned from the API.


Notes

Unlike the Jupyter notebook deployed on Heroku, we can have multiple people interact with the website all at the same time. This is possible because:

API created with Lambda and Gateway API automatically scales up as multiple POST requests are made.
The website data and UI are fetched and rendered to each of the users locally - html, css, and JavaScript code is downloaded to each of the users' browsers and rendered locally.
