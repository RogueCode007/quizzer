### Steps to run the aplication locally: 
1. Download the code or clone the repository on your local machine. 
2. Navigate into the project folder via your terminal and run "npm install" to install all dependencies.
3. After successful installation, run "npm run serve", a server will be launched and the application will be live on port 8000 on your local machine 


#### Steps to deploy the application on heroku: 
1. Run 'git init' to initialize a remote repository.
2. Run 'git add .' to add all your project files.
3. Run 'git commit', then enter a commit message.
4. Create a 'static.json' file in the root of the project folder and paste the following code
###
{
  "root": "dist",
  "clean_urls": true,
  "routes": {
    "/**": "index.html"
  }
}
###
5. Add the newly added file to git by running 'git add static.json' and also run 'git commit'
6. Assuming you have heroku CLI setup on your PC. Run the following code ;
heroku login
heroku create
heroku buildpacks:add heroku/nodejs
heroku buildpacks:add https://github.com/heroku/heroku-buildpack-static
git push heroku master

7. Heroku will build and deploy your application and provide the live address.


### Technologies used include;
1. SCSS
2. Tailwind CSS
3. Vue
4. Vuex for state management
5. Vue router


## WHAT WILL I DO TO ENABLE THE APP SCALE AND IF GIVEN MORE TIME
1. I would make the allocated time for a quiz session dynamic so a user can input a desired time slot 
2. I would add a feature that would enable a user to add quiz questions, although that would most likely mean consuming an API from the backend.
3. I would customize a loading page or ring that comes up immediately the quiz has ended, just before the results are displayed since submitting the test results would most likely mean making a post request to the backend which might take a few seconds.
4. I would add a progress bar so someone taking the quiz would have an idea of how close or far they are from the end of the quiz.
5. I would add a previous button so previously answered questions can be visited and answers changed.
6. I would also rework the overall design.
7. I would also fetch and fil the app data from a get API request to the backend rather than hardcoding it in.
8. I would make out time to add comments to my code if i had more time
9. I also feel the UI can be improved
