#Steps to run the aplication locally: 
1. Download the code or clone the repository on your local machine. 
2. Navigate into the project folder via your terminal and run "npm install" to install all dependencies.
3. After successful installation, run "npm run serve", a server will be launched and the application will be live on port 8000 on your local machine 


#Steps to deploy the application on github pages: 
1. Creat a 'vue.config.js' file in the root of your project, then paste the code below in it 

#####
module.exports = {
  publicPath: process.env.NODE_ENV === 'production'
    ? '/my-project/'
    : '/'
}
####

Note: If you are deploying to https://<USERNAME>.github.io/ or to a custom domain, you can omit publicPath as it defaults to "/".

If you are deploying to https://<USERNAME>.github.io/<REPO>/, (i.e. your repository is at https://github.com/<USERNAME>/<REPO>), set publicPath to "/<REPO>/". For example in the code above, the repo name is "my-project". 

2. Inside your project root folder, create a 'deploy.sh' file and paste the following code in it


#####
#!/usr/bin/env sh

# abort on errors
set -e

# build
npm run build

# navigate into the build output directory
cd dist

# if you are deploying to a custom domain
# echo 'www.example.com' > CNAME

git init
git add -A
git commit -m 'deploy'

# if you are deploying to https://<USERNAME>.github.io
# git push -f git@github.com:<USERNAME>/<USERNAME>.github.io.git master

# if you are deploying to https://<USERNAME>.github.io/<REPO>
# git push -f git@github.com:<USERNAME>/<REPO>.git master:gh-pages

cd -

Uncomment the highlighted lines as appropriate and run the commands in your terminal
(This just means if you're deploying to "https://<USERNAME>.github.io/<REPO>", you'll uncomment
line 48 and run all the commands in the deploy.sh file, including the uncommented line.)