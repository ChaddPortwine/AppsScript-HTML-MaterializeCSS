# AppsScript-HTML-Starter
<h2>Overview</h2>

Create and Host a website with Apps Script. Work locally using your favorite IDE. Use HTML, CSS, and JavaScript to design your pages. Use `clasp` to push your code files to Google Drive and to deploy your site to Google Cloud Platform.

This project uses npm to install clasp. The clasp CLI lets you work on Google Apps Scripts locally and then push and deploy changes from your Terminal or IDE.

It is recommened you create a new repository using GitHub's <a href="https://help.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-repository-from-a-template">template feature</a>. Your new repository will contain this project's files and folder structure, but you will have a fresh history of changes.   

<h2>Instructions</h2>

<h3>Create a new repository from a template</h3>

Above the README and file list in this GitHub repository, click <b>Use this template</b>. Chose the settings that fit your needs.

<h3>Clone your new repository and install clasp</h3>

```
git clone git@github.com:<YOUR_GITHUB>/<YOUR_REPO_NAME>
cd AppsScript-HTML-Starter
npm install
```
<h3>Give clasp permission to use your account</h3>

Run `clasp login`. This will open a browser where you must login and click through to grant clasp access to a few Google services. Once complete, return to your terminal or IDE.

<h3>Enable the Google Apps Script API</h3>
Open your Apps Script user settings.

https://script.google.com/home/usersettings

Turn on Google Apps Script API and return to your terminal or IDE.

<h3>Create a new Apps Script Web App</h3>

Use `clasp` to create a new blank Apps Script project. Set the type, title, and directory.
```
clasp create --type webapp --title "AppsScript-HTML-Starter" --rootDir ./
```

<h3>Push your local files to Google Drive.</h3>

Run `clasp push` to send your changes to Google Drive (aka script.google.com).


```
clasp push
? Manifest file has been updated. Do you want to push and overwrite? (y/N)

```
Enter `y` to push and overwrite. Your local manifest file, `appsscript.json`, will configure your Apps Script project to run as a Web App that can host your website.

```
└─ Code.gs
└─ appsscript.json
└─ index.html
Pushed 3 files.
```

<h3>Deploy your app to Google Cloud Platform</h3>

Run `clasp deploy` to deploy your app to GCP. Within your project, a new version is created and then published.

```
clasp deploy
Created version 1.
- AKf...LEQ @1.
```
<h3>Open the Web Page</h3>

Run `clasp open --webapp` and use arrow keys to select the version you just created.

```
clasp open --webapp
? Open which deployment? (Use arrow keys)
❯                               @HEAD - AKf...h2S
```

If everything worked, you should see the <b>Hello Apps Script!</b> welcome page in your browser.

<h2>Make Changes to your Website</h2>
<h3>Edit the index.html file.</h3>

To make changes to your website, you will edit the `index.html`.

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>title</title>
  </head>
  <body>
    <h1>Hello Apps Script!</h1>
    <p>Here is a new line of text</p>
  </body>
</html>
```
<h3>Push and deploy your updated Website.</h3>

Save your changes to index.html. Run `clasp push` to send your changes to Google Drive (aka script.google.com).

```
clasp push
└─ Code.gs
└─ appsscript.json
└─ index.html
Pushed 3 files.
```
Run `claps deploy` to deploy your app to GCP. Within your project, a new version is created and then published. 

```
clasp deploy
Created version 2.
- AZf...INv @2.
```
<h3>Open the Web Page</h3>

Run `clasp open --webapp` and use arrow keys to select the version you just created.
```
clasp open --webapp
? Open which deployment? (Use arrow keys)
❯                               @HEAD - AKf...h2S
❯                               @1 - AKf...h2S
❯                               @2 - AZf...INv
```
If everything worked, you should see the <b>Hello Apps Script!</b> welcome page in your browser with the <b>new line of text</b>.

