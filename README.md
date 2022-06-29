# [Bodybuild]()

## Contents
1. [Summary](#summary)
1. [UX](#ux)
    1. [Strategy](#strategy)
    1. [Scope](#scope)
    1. [Structure](#structure)
    1. [Skeleton](#skeleton)
    1. [Surface](#surface)
1. [Features](#features)
    1. [Existing Features](#existing-features)
    1. [Features left to implement](#left-to)
1. [Bugs](#bugs)
1. [Technologies used](#tech)
1. [Testing](#testing)
1. [Deployment](#deployment)
    1. [Github Pages](#github)
    1. [heroku](#heroku)
1. [Credits](#credits)
    1. [Content](#content)
    1. [Acknowledgements](#acks)

# <a name="summary"></a> Summary


# <a name="ux"></a> UX
## <a name="Strategy"></a> Strategy
### **New site user's goals:**

* As a new site user, I want to be able to understand the intent of the page
* As a new site user, I want to understand easily how to navigate the page and access the facilities provided
### **Returning user's goals**
* As a returning site user, I want to be able to log in

### **Site owner'as goals:**

## <a name="scope"></a> Scope
**Functional requirements:**
#### For ease of use:
* Navigation bar which is simple and easy to navigate
* A search Function
#### To ensure the database is up to date and editable

**Content requirements:**
#### To ensure the site is visually appealing and to draw the user's eye:

* Clear, crisp colours which do not detract from or make the text unreadable


## <a name="structure"></a> Structure
**Interaction design:**
* User friendly interface to ensure usability and to encourage the user to return
* Responsive and visible links which change on hover to provide user feedback as they navigate the site
* Ability to exit pop ups so a user is not forced to use the browser navigation tools

**Information Architecture:**
* Navigation bar at the top of the page
* Footer at the bottom of the page - sticky to the bottom so it is only visible when the bottom of the page is reached
* Responsive navigation bar - adjusting for mobile for ease of use
* Responsive images to ensure they fit within the designated spaces, no matter what device is being used or the size of the screen
* All features appropriate size and responsive for mobile and desktop viewing
* All information is appropriate and relative to the subject and not misleading or hard to find

## <a name="skeleton"></a> Skeleton
Please click the below link to view the wireframe mock up of the website in mobile, tablet and desktop sizing

[Wireframe]()

## <a name="surface"></a> Surface
The intention of the website is to be clean, crisp and clear

# <a name="tech"></a> Technologies Used
* Materialize - https://materializecss.com/
* JavaScript
* Google fonts - https://fonts.google.com/
* www.validator.w3.org
* http://www.css-validator.org/
* Git
* Gitpod
* GitHub
* Google Chrome
* http://www.responsinator.com/
* Chrome Dev Tools
* Python
* Flask
* Amazon AWS S3
* MongoDb
* Heroku
* Jinja
* Favicon.io
* Balsamiq

# <a name="testing"></a> Testing

### **Performance testing:**
1. Tested website responsiveness using http://www.responsinator.com/
    1. Results: The website is responsive to all device sizes without any unnecessary x-scroll. 
1. Tested the image size to ensure no image is to large and impacting the website loading times. I used the Google Dev Tools - Network
    1. Results: The site loading time is sub optimal. The total website loading time is 1.30s which can be improved
1. Tested the images on the all recipes page using Google Dev Tools - Lighthouse
    1. Results: An issue highlighted using this tool is the image formats used. Image formats like JPEG 2000, JPEG XR, and WebP often provide better compression than PNG or JPEG, which means faster downloads and less data consumption.
1. All HTML pages were tested using https://jigsaw.w3.org/css-validator/validator
    1. All but the 'base' template resulted in errors that the Lang Doctype and Title were missing. This was to be expected as the details were being extended from the base template to did not need to be added
    1. All HTML pages resulted in errors where the Jinja template language was used
    1. None of these are actual errors within the code
1. Tested the CSS using http://www.css-validator.org/
    1. No errors were found
1. Tested the website on the Google Chrome browser Version 87.0.4280.88 (Official Build) (64-bit)
    1. Results: The website was responsive and the elements performed in the way they were intended to
1. Tested the website on the Microsoft Edge browser Version Version 87.0.664.66 (Official build) (64-bit)
    1. Results: The website was responsive and the elements performed in the way they were intended to
1. Tested the website on the Firefox browser Version 82.0.3 (64-bit)
    1. Results: The website was responsive and the elements performed in the way they were intended to
1. Tested the form validation worked correctly on each of the above browsers
    1. Results: The form correctly sent when the fields were completed as they should have been and did not when the fields had not been completed

# <a name="deployment"></a> Deployment
## <a name="github"></a> Github Pages
1. Create a new repository or access an existing repository
1. Click the green Gitpod button to launch the project in Gitpod
1. Create an index.html file
1. Add the file to the staging area using the git add Functional
1. Commit the file using the git commit function, adding an appropriate commentary
1. Push the file to GitHub using the git commit and git push functions
1. Refresh your GitHub repository and click the 'Settings' tab
1. Scroll to the GitHub Pages section and select a publishing source
1. Click 'Save'
1. Click the URL created within the Settings - GitHub Pages section

**To clone the repository for local deployment:** 
1. On the main page of the repository, click the down arrow Code button
1. Click the download icon under the relevant section to clone with either HTTPS, SSH or GitHub CLI 
1. In Git Bash, change the current directory to the location you want the directory to be stored
1. Type git clone and then paste the URL you copied in step 2
    1. An example for HTTPS: `git clone`
1. Press enter - that's it, your clone has been completed! 

**To fork the repository:**
1. Navigate to the main page of the repository you wish to fork
1. Click the Fork button on the top right hand side of the page
## <a name="heroku"></a> Heroku
### How to deploy to Heroku

To deploy the app to Heroku from its [GitHub repository](), the following steps were taken:

1. From the GitPod terminal, create **requirements.txt** and **Procfile** using these commands:

```console
pip3 freeze --local > requirements.txt
echo web: python app.py > Procfile
```

2. **Push** these files to GitHub
3. **Log In** to [Heroku](https://id.heroku.com/login)
4. Select **Create new app** from the dropdown in the Heroku dashboard
5. Choose a unique name ('Bodybuild') for the app and the location nearest to you
6. Go to the **Deploy** tab and under **Deployment method** choose GitHub
7. In **Connect to GitHub** enter your GitHub repository details and once found, click **Connect**
8. Go to the **Settings** tab and under **Config Vars** choose **Reveal Config Vars**
9. Enter the following keys and values, which must match those in the env.py file created earlier:

|**Key**|**Value**|
|:-----|:-----|
|IP|`0.0.0.0`|
|PORT|`5000`|
|SECRET_KEY|`<app secret key>`|
|MONGO_URI|mongodb+srv://constantin:<password>@bodybuild.grjlb.mongodb.net/?retryWrites=true&w=majority
|MONGO_DBNAME|`Bodybuild`|
|S3_BUCKET|`bodybuild-image-repo`|
|S3_ACCESS_KEY|`<S3 key>`|
|S3_SECRET_ACCESS_KEY|`<S3 secret key>`|

10. Go back to the **Deploy** tab and under **Automatic deploys** choose **Enable Automatic Deploys**
11. Under **Manual deploy**, select **master** and click **Deploy Branch**
12. Once the app has finished building, click **Open app** from the header row of the dashboard

# <a name="credits"></a> Credits
## <a name="content"></a> Content


## <a name="acks"></a> Acknowledgements

* My mentor Antonio Rodriguez who has provided me with guidance and support through the project