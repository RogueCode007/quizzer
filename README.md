### Steps to run the aplication locally: 
1. Download the code or clone the repository on your local machine. 
2. Navigate into the project folder via your terminal and run "npm install" to install all dependencies.
3. After successful installation, run "npm run serve", a server will be launched and the application will be live on port 8000 on your local machine 


#### Steps to deploy the application on netlify: 
1. Create a netlify account and give  netlify access to your github repositories
2. Create a new repository on github, copy the repo URL,usually ends with '.git'
3. In your terminal , run 'git add .' to add all your project files.
3. Run 'git commit', then enter a commit message.
4. Run 'git remote add origin <repourl>' you copied in step 2
5. Push your changes by running 'git push -f origin master'
6. Now on your netlify dashboard, choose to deploy an app from github and select the repository to which you just pushed your project files to.
7. Set the build command as npm run build or yarn run build as the case may be
8. Set the publish directory as dist
9. Hit deploy and netlify will build and host your site live. Any new changes made and pushed to that repo will also automatically be deployed by netlify



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
