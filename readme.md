# Real-time Tweet Stream
###### Using Node.js to stream real-time tweets to a map

Author: [**Brian G. Katz**](https://github.com/briangkatz) | Oregon State University | Summer 2018

*Inspired by: [Bo Zhao](https://github.com/jakobzhao/geog371/tree/master/lectures/lec20) and [Stewart Harper](https://blog.safe.com/2014/03/twitter-stream-api-map/)*

##### *NOTE: This tutorial requires Twitter Developer API credentials ([apply here](https://developer.twitter.com/en/apply/user)). The application process can take up to a few days from the time you apply for credentials to the time you receive your unique keys. It is therefore recommended that you FIRST apply for your credentials before beginning this tutorial.*

[Tutorial](https://www.github.com/briangkatz/realtime-tweets)

[Live Demo](https://realtime-tweet-stream.herokuapp.com)

## Overall Workflow

1. Download Node.js
2. Clone this repository
3. Run `npm install` from command line inside repository root folder `.../realtime-tweets`
4. Open `app.js` in your preferred IDE (e.g. WebStorm)
5. Enter your [Twitter API credentials](https://apps.twitter.com/) in `app.js`
6. Run `app.js` in either your IDE or command line
7. Open your web browser and visit `localhost:3000`
8. (Optional) Deploy your live app on Heroku

---

## Detailed Instructions

#### Step 1: Download Node.js

- https://nodejs.org/en/download/
- Add the path to the `node.exe` file to your System Environment Variables
  - For Windows PC users:
    - Search "Edit the system environment variables"
    - Click `Environment Variables...`
    - Under `System variables`, click `Path` then `Edit...`
    - Click `New` and add the path containing the `node.exe` file
      - e.g. `C:\Program Files\nodejs`
    - Click `OK`, `OK`, and `OK` to save changes

#### Step 2: Clone repository

- Download [Git](https://git-scm.com/downloads) if you have not already done so
- Add Git to your System Environment Variables like above Node.js example
- Visit `https://github.com/briangkatz/realtime-tweets`
- Click `Clone or download`
- Copy the clone URL: `https://github.com/briangkatz/realtime-tweets.git`
- In your command line, navigate to a location where you want the cloned repository to reside
  - e.g. `cd C:\Workspace`
- Enter `git clone` then paste the clone URL
  - e.g. `git clone https://github.com/briangkatz/realtime-tweets.git`
- Press `Enter` to clone the repository files to your local drive

#### Step 3: Run `npm install`

- In your command line, navigate to the repository root folder
  - e.g. `cd C:\Workspace\realtime-tweets`
- Type `npm install` and press `Enter`
  - This will begin installing the required Node.js libraries (dependencies) that are specified in the `package.json` file
  - These dependencies include:
    - `express`
    - `socket.io`
    - `twitter`
  - These Node.js libraries are ***essential*** for the next steps to be completed successfully

#### Step 4: Open `app.js` in IDE

- Open your preferred Integrated Development Environment (IDE)
  - e.g. [WebStorm](https://www.jetbrains.com/webstorm/)
- First, open the `realtime-tweets` repository as a `New Project` in a `New Window`
  - WebStorm instructions:
    - Click `Open`
    - Select the `realtime-tweets` folder
    - Click `OK`
    - Click `Open in New Window`
- Then, open the file `app.js` by double-clicking it

#### Step 5: Enter Twitter API credentials

- Apply for a Twitter Developer API [here](https://developer.twitter.com/en/apply/user) if you have not already done so

  - *NOTE: This process can take up to a few days from the time you apply for Twitter API credentials to the time you receive your unique keys required for this step.*

- In the `app.js` file, lines 9-16 appear as follows:

  ```javascript
  // Set-up Twitter stream API
  var twit = new twitter({
    consumer_key: '<ENTER>',
    consumer_secret: '<ENTER>',
    access_token_key: '<ENTER>',
    access_token_secret: '<ENTER>'
  }),
  stream = null;
  ```

- Replace the four instances of `<ENTER>` in lines 11-14 with your Twitter API credentials:

  - `consumer_key`
  - `consumer_secret`
  - `access_token_key`
  - `access_token_secret`
    - These can be found under the `Keys and Access Tokens` section of your Application Management dashboard (https://apps.twitter.com)

#### Step 6: Run `app.js`

- ***NOTE: This step can be performed in either your 1) IDE or 2) command line***
  - **Option 1)** IDE (WebStorm) instructions:
    - With your mouse cursor inside the `app.js` file:
      - `right-click`
      - Click `Run 'app.js'`
  - **Option 2)** Command line instructions:
    - With your command line open:
      - Navigate to the repository root folder
        - e.g. `cd C:\Workspace\realtime-tweets`
      - Type `node app` and press `Enter`

#### Step 7: Open `localhost:3000` in browser

- Open your web browser ([Chrome](https://www.google.com/chrome/) is recommended)
- Enter `localhost:3000` in your address bar and press `Enter`
- You should now see a map being populated by tweet locations in real-time
  - Congratulations!

#### Step 8 (optional): Deploy live app with Heroku

- Create a GitHub repository for your version of the cloned `realtime-tweets` repo
  - This is the product of Steps 1-7 above
- Create a Heroku account [here](https://www.heroku.com/)
- Download and install the [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli#download-and-install)
- Login to your Heroku online dashboard
- Click `New`, then `Create new app`
- Choose a name for your app and click `Create app`
  - This name will become part of your app's URL (e.g. https://[app-name].herokuapp.com)
- In the `Deploy` tab of your Heroku dashboard, find the `Deployment method` section
- Click `GitHub / Connect to GitHub`
- Search for the GitHub repository you created at the beginning of this step, and then click `Connect`
- Click `Enable Automatic Deploys` to synchronize your `git commit` changes with your Heroku app
- In the `Settings` tab of your Heroku dashboard, fipush` your repo changes
- Click `Add buildpack`, select `nodejs`, and then click `Save changes`
- Finally, `git add`, `git commit`, and `git push` the changes you made to your repository
- Back in your Heroku dashboard, click `Open app` to load your live, real-time tweet map!

---

## Resources

- GEOG 371: Web Mapping course materials by Bo Zhao at Oregon State University ([GitHub](https://www.github.com/jakobzhao/geog371))
- Blog post by Stewart Harper ([blog.safe](https://blog.safe.com/2014/03/twitter-stream-api-map/))
- Node.js ([download](https://nodejs.org/en/download/))
- Twitter Developer API ([apply here](https://developer.twitter.com/en/apply/user))
- JetBrains WebStorm ([download](https://www.jetbrains.com/webstorm/))
- Git ([download](https://git-scm.com/downloads))
- Google Chrome ([download](https://www.google.com/chrome/))
- [Heroku](https://www.heroku.com/)