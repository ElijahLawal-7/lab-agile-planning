<!DOCTYPE html>
<!-- saved from url=(0171)https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-CD0116EN-SkillsNetwork/labs/module_2/lab_1/lab1-get-set-up-in-zenhub.md.html?origin=www.coursera.org -->
<html lang="en"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="./lab1-get-set-up-in-zenhub_files/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    <link rel="stylesheet" href="./lab1-get-set-up-in-zenhub_files/default.min.css">
  <style type="text/css">/* this file is used for labs on cognitiveclass.ai that were written in markdown */

/* applies to images, i.e. "![]()" in markdown */
img {
  max-width: 100%;
  height: auto;
}

/* add padding and margins */
body {
  padding: 10px;
  margin: 10px;
}

/* applies to tables, i.e. "|--|--|" in markdown */
table td,
table th {
  padding: 0.75rem;
  vertical-align: top;
  border-top: 1px solid #dee2e6;
}

/* applies to using quotes, i.e. ">" in markdown */
blockquote {
  background: #f9f9f9;
  border-left: 10px solid #ccc;
  margin: 1.5em 10px;
  padding: 1em 10px 0.1em 10px;
  quotes: '\201C''\201D''\2018''\2019';
}

/* the headers need some spacing */

h1,
h2,
h3,
h4,
h5,
h6 {
  font-weight: 500;
  padding-top: 20px;
}

/* Add padding between nested list item */
ul > li > ul {
  padding-bottom: 1rem;
}

.code-badge-language {
  display: none;
}
.code-badge-copy-icon {
  background: url('data:image/svg+xml;base64,PHN2ZyBhcmlhLWhpZGRlbj0idHJ1ZSIgZm9jdXNhYmxlPSJmYWxzZSIgZGF0YS1wcmVmaXg9ImZhciIgZGF0YS1pY29uPSJjb3B5IiBjbGFzcz0ic3ZnLWlubGluZS0tZmEgZmEtY29weSBmYS13LTE0IiByb2xlPSJpbWciIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgdmlld0JveD0iMCAwIDQ0OCA1MTIiPjxwYXRoIGZpbGw9ImN1cnJlbnRDb2xvciIgZD0iTTQzMy45NDEgNjUuOTQxbC01MS44ODItNTEuODgyQTQ4IDQ4IDAgMCAwIDM0OC4xMTggMEgxNzZjLTI2LjUxIDAtNDggMjEuNDktNDggNDh2NDhINDhjLTI2LjUxIDAtNDggMjEuNDktNDggNDh2MzIwYzAgMjYuNTEgMjEuNDkgNDggNDggNDhoMjI0YzI2LjUxIDAgNDgtMjEuNDkgNDgtNDh2LTQ4aDgwYzI2LjUxIDAgNDgtMjEuNDkgNDgtNDhWOTkuODgyYTQ4IDQ4IDAgMCAwLTE0LjA1OS0zMy45NDF6TTI2NiA0NjRINTRhNiA2IDAgMCAxLTYtNlYxNTBhNiA2IDAgMCAxIDYtNmg3NHYyMjRjMCAyNi41MSAyMS40OSA0OCA0OCA0OGg5NnY0MmE2IDYgMCAwIDEtNiA2em0xMjgtOTZIMTgyYTYgNiAwIDAgMS02LTZWNTRhNiA2IDAgMCAxIDYtNmgxMDZ2ODhjMCAxMy4yNTUgMTAuNzQ1IDI0IDI0IDI0aDg4djIwMmE2IDYgMCAwIDEtNiA2em02LTI1NmgtNjRWNDhoOS42MzJjMS41OTEgMCAzLjExNy42MzIgNC4yNDMgMS43NTdsNDguMzY4IDQ4LjM2OGE2IDYgMCAwIDEgMS43NTcgNC4yNDNWMTEyeiI+PC9wYXRoPjwvc3ZnPg==');
  background-size: 100% 100%;
}

.code-badge {
  bottom: 0 !important;
  top: unset !important;
  background: unset !important;
}

.code-badge > .code-badge-check-icon {
  background: green;
}
.code-badge-check-icon {
  font-size: 1.2em;
  cursor: pointer;
  padding: 0 7px;
  background: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGFyaWEtaGlkZGVuPSJ0cnVlIiBmb2N1c2FibGU9ImZhbHNlIiBkYXRhLXByZWZpeD0iZmFzIiBkYXRhLWljb249ImNoZWNrIiBjbGFzcz0ic3ZnLWlubGluZS0tZmEgZmEtY2hlY2sgZmEtdy0xNiIgcm9sZT0iaW1nIiB2aWV3Qm94PSIwIDAgNTEyIDUxMiIgc3R5bGU9IiYjMTA7ICAgIGNvbG9yOiAjMmFmZjMyOyYjMTA7Ij48cGF0aCBmaWxsPSJjdXJyZW50Q29sb3IiIGQ9Ik0xNzMuODk4IDQzOS40MDRsLTE2Ni40LTE2Ni40Yy05Ljk5Ny05Ljk5Ny05Ljk5Ny0yNi4yMDYgMC0zNi4yMDRsMzYuMjAzLTM2LjIwNGM5Ljk5Ny05Ljk5OCAyNi4yMDctOS45OTggMzYuMjA0IDBMMTkyIDMxMi42OSA0MzIuMDk1IDcyLjU5NmM5Ljk5Ny05Ljk5NyAyNi4yMDctOS45OTcgMzYuMjA0IDBsMzYuMjAzIDM2LjIwNGM5Ljk5NyA5Ljk5NyA5Ljk5NyAyNi4yMDYgMCAzNi4yMDRsLTI5NC40IDI5NC40MDFjLTkuOTk4IDkuOTk3LTI2LjIwNyA5Ljk5Ny0zNi4yMDQtLjAwMXoiLz48L3N2Zz4=');
  background-size: 100% 100%;
}
</style></head>
  <body>
    <h1>Lab 1: Get set up in ZenHub</h1>
    <p><strong>Estimated time needed:</strong> 20 minutes</p>
    <p>In this lab, you will prepare for the labs that follow by setting up a free GitHub account and a free ZenHub account.</p>
    <h2>Objectives</h2>
    <p>After completing this lab, you will be able to:</p>
    <ol>
      <li>Create a free GitHub account.</li>
      <li>Create a GitHub repository.</li>
      <li>Create a free ZenHub account.</li>
      <li>Install the optional browser extension for ZenHub.</li>
    </ol>
    <h2>Exercise 1 : Create a free GitHub account</h2>
    <p>In this exercise, you will create a free GitHub account, if you don't already have one. ZenHub requires GitHub so this first step is a prerequisite to getting a ZenHub account.</p>
    <ol>
      <li>
        <p>Go to <a href="http://github.com/" target="_blank" rel="external">GitHub.com</a> and sign up for a free GitHub account.</p>
      </li>
      <li>
        <p>Enter your email address and press the <strong>Sign up for GitHub</strong> button. If you have an account, press the <strong>Sign in</strong> button and login.</p>
        <p>
          <img src="./lab1-get-set-up-in-zenhub_files/lab1-github-sign-up.png" alt="Github signup screen">
        </p>
      </li>
    </ol>
    <h2>Exercise 2 : Create a GitHub repository</h2>
    <p>In this exercise, you will create a repository to hold the issues and kanban board for your plan.</p>
    <ol>
      <li>
        <p>
          If you just created your GitHub account, create your first repository by pressing the <strong>Create repository</strong> button, then go to step <strong>3</strong>.
          
          <img src="./lab1-get-set-up-in-zenhub_files/lab1-github-create-repository.png" alt="create repository">
        </p>
      </li>
      <li>
        <p>
          If you already have a GitHub account, sign into GitHub and on your account page, press the <strong>New</strong> repository button.
          
          <img src="./lab1-get-set-up-in-zenhub_files/lab1-github-new-repository.png" alt="new repository">
        </p>
      </li>
      <li>
        <p>
          Name your repository <strong>lab-agile-planning</strong> and give it a good description like: <em>This repository contains the lab for agile planning</em> and make sure the <strong>Public</strong> option is selected.
          
          <img src="./lab1-get-set-up-in-zenhub_files/lab1-github-name-repository.png" alt="name repository">
        </p>
      </li>
      <li>
        <p>
          Scroll down on that page and select <strong>Add a README file</strong> and then press the <strong>Create repository</strong> button to create the new repository.
          
          <img src="./lab1-get-set-up-in-zenhub_files/lab1-github-press-create.png" alt="press create">
        </p>
      </li>
    </ol>
    <p>
      You should now have a new repository called <strong>lab-agile-planning</strong> that we will use with ZenHub. It should look similar to the screenshot below:
      
      <img src="./lab1-get-set-up-in-zenhub_files/lab1-github-repository-created.png" alt="repository created">
    </p>
    <h2>Exercise 3 : Create free ZenHub account</h2>
    <p>In this exercise, you will create a free ZenHub account to use with GitHub. ZenHub is an application that integrates with GitHub. In order to use it, you must sign up for a free account.</p>
    <ol>
      <li>
        <p>Go to <a href="http://www.zenhub.com/?utm_medium=Exinfluencer&amp;utm_source=Exinfluencer&amp;utm_content=000026UJ&amp;utm_term=10006555&amp;utm_id=NA-SkillsNetwork-wwwcourseraorg-SkillsNetworkCoursesIBMCD0116ENSkillsNetwork28298839-2022-01-01" target="_blank" rel="external">www.zenhub.com</a> and press the <a href="https://www.zenhub.com/sign-up?utm_medium=Exinfluencer&amp;utm_source=Exinfluencer&amp;utm_content=000026UJ&amp;utm_term=10006555&amp;utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMCD0116ENSkillsNetwork28298839-2022-01-01" target="_blank" rel="external">Try for free</a> button. Even though it says "<em>Start your free 14-day trial with ZenHub</em>" you can continue to use ZenHub for free on open source projects.</p>
        <p>
          <img src="./lab1-get-set-up-in-zenhub_files/lab1-zenhub-homepage.png" alt="ZenHub home page">
        </p>
      </li>
      <li>
        <p>On the next page, you need to enter your Email ID and a strong Password to create a new ZenHub account.</p>
        <p>
          <img src="./lab1-get-set-up-in-zenhub_files/lab1-sign-up.png" alt="get started">
        </p>
      </li>
    </ol>
    <blockquote>
      <p>Note: Alternate way, press the <strong>Sign up with Google</strong> button if you have a google account already and want to use that on ZenHub and then login using your Google/Gmail credentials.</p>
    </blockquote>
    <ol>
      <li>
        <p>Enter whatever you want for this ZenHub survey and press <strong>Submit</strong></p>
        <p>
          <img src="./lab1-get-set-up-in-zenhub_files/lab1-zenhub-survey.png" alt="survey">
        </p>
      </li>
      <li>
        <p>On the next page, enter your organization name.</p>
        <p>
          <img src="./lab1-get-set-up-in-zenhub_files/lab1-org.png" alt="organization">
        </p>
      </li>
      <li>
        <p>Next, you will be asked to create a workspace. Assign the name "<strong>Development</strong>" to your new ZenHub workspace.</p>
        <p>
          <img src="./lab1-get-set-up-in-zenhub_files/lab1-workspace.png" alt="workspace name">
        </p>
      </li>
      <li>
        <p>
          Go to your kanban Board, and click on <strong>Connect your GitHub account</strong> button.
          
          <img src="./lab1-get-set-up-in-zenhub_files/lab1-connect-to-github.png" alt="sign in">
        </p>
      </li>
      <li>
        <p>
          Since you are already signed into GitHub from the previous steps, you should be presented with a page that will allow you to authorize ZenHubIO to access your GitHub account.
          
          <img src="./lab1-get-set-up-in-zenhub_files/lab1-zenhub-authorize-zenhubio.png" alt="authorize zenhub">
        </p>
      </li>
      <li>
        <p>
          (optional) If you are not signed into GitHub, you will be prompted to sign in to GitHub. That will bring you to a page where you must use your GitHub credentials.
          
          <img src="./lab1-get-set-up-in-zenhub_files/lab1-zebhub-github-credentials.png" alt="github credentials">
        </p>
      </li>
      <li>
        <p>
          If you have two-factor authentication enabled on your GitHub account, you must enter your authorization code now.
          
          <img src="./lab1-get-set-up-in-zenhub_files/lab1-zenhub-two-factor-auth.png" alt="two factor auth">
        </p>
      </li>
      <li>
        <p>
          Accept ZenHub's privacy policy
          
          <img src="./lab1-get-set-up-in-zenhub_files/lab1-zenhub-privacy-policy.png" alt="privacy policy">
        </p>
      </li>
      <li>
        <p>
          On your kanban board, click on <strong>Add repositories</strong> to add add repositories to Development workspace.
          
          <img src="./lab1-get-set-up-in-zenhub_files/lab1-add-repo.png" alt="add repos">
        </p>
      </li>
      <li>
        <p>
          On the next page, click on <strong>Add repos</strong> under connect repositories.
          
          <img src="./lab1-get-set-up-in-zenhub_files/lab1-add-repo2.png" alt="add repos">
        </p>
      </li>
      <li>
        <p>Select <strong>lab-agile-planning</strong> repository that you created in the previous steps, then click on <strong>Add</strong>.</p>
      </li>
      <li>
        <p>
          This will place you in your kanban board for the <code>lab-agile-planning</code> repository.
          
          <img src="./lab1-get-set-up-in-zenhub_files/lab1-zenhub-kanban-board.png" alt="kanban board">
        </p>
      </li>
    </ol>
    <h2>Exercise 4 : (Optional) Browser extension for Chrome or Firefox</h2>
    <p>In this optional exercise, you will download a browser extension for ZenHub.</p>
    <p>If you use Chrome or Firefox, you can download a browser extension for ZenHub that will add a ZenHub tab while you are using GitHub so that you don't have to go to zenhub.com to view your kanban board.</p>
    <ol>
      <li>Download a browser extension for ZenHub here: <a href="https://www.zenhub.com/extension?utm_medium=Exinfluencer&amp;utm_source=Exinfluencer&amp;utm_content=000026UJ&amp;utm_term=10006555&amp;utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMCD0116ENSkillsNetwork28298839-2022-01-01" target="_blank" rel="external">www.zenhub.com/extension</a>. Once installed, it will add a ZenHub tab while you are using GitHub. This is purely a convenience. The capabilities of both the browser extension and the web zenhub.com site are the same.</li>
    </ol>
    <h2>Summary</h2>
    <p>Congratulations! You are now set up with a ZenHub account and GitHub account so that you can work through the rest of the labs.</p>
    <h2>Author(s)</h2>
    <p><a href="https://www.coursera.org/instructor/johnrofrano?utm_medium=Exinfluencer&amp;utm_source=Exinfluencer&amp;utm_content=000026UJ&amp;utm_term=10006555&amp;utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMCD0116ENSkillsNetwork28298839-2022-01-01" target="_blank" rel="external">John Rofrano</a></p>
    <h2>Changelog</h2>
    <table>
      <thead>
        <tr>
          <th>Date</th>
          <th>Version</th>
          <th>Changed by</th>
          <th>Change Description</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>2021-08-03</td>
          <td>0.1</td>
          <td>John Rofrano</td>
          <td>Initial version created</td>
        </tr>
        <tr>
          <td>2022-04-27</td>
          <td>0.2</td>
          <td>Srishti Srivastava</td>
          <td>Updated steps as per new ZenHub sign up</td>
        </tr>
        <tr>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
        </tr>
      </tbody>
    </table>
    <h2></h2>
    <h3 align="center">© IBM Corporation 2021. All rights reserved.</h3>
    <h3></h3>
    <script>window.addEventListener('load', function() {
snFaculty.inject();
});</script>
    <script src="./lab1-get-set-up-in-zenhub_files/inject.43989f87.js.download"></script>
    <script src="./lab1-get-set-up-in-zenhub_files/highlight.min.js.download"></script>
    <script src="./lab1-get-set-up-in-zenhub_files/highlightjs-badge.min.js.download"></script>
  

<style>
@media print {
   .code-badge { display: none; }
}
    .code-badge-pre {
        position: relative;
    }
    .code-badge {
        display: flex;
        flex-direction: row;
        white-space: normal;
        background: transparent;
        background: #333;
        color: white;
        font-size: 0.875em;
        opacity: 0.5;
        transition: opacity linear 0.5s;
        border-radius: 0 0 0 7px;
        padding: 5px 8px 5px 8px;
        position: absolute;
        right: 0;
        top: 0;
    }
    .code-badge.active {
        opacity: 0.8;
    }

    .code-badge:hover {
        opacity: .95;
    }

    .code-badge a,
    .code-badge a:hover {
        text-decoration: none;
    }

    .code-badge-language {
        margin-right: 10px;
        font-weight: 600;
        color: goldenrod;
    }
    .code-badge-copy-icon {
        font-size: 1.2em;
        cursor: pointer;
        padding: 0 7px;
        margin-top:2;
    }
    .fa.text-success:{ color: limegreen !important }
</style><div id="CodeBadgeTemplate" style="display:none">
    <div class="code-badge">
        <div class="code-badge-language">{{language}}</div>
        <div title="Copy to clipboard">
            <i class="{{copyIconClass}} code-badge-copy-icon"></i>
        </div>
     </div>
</div></body></html>