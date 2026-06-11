# Git steps - git howto
2026-06-11


##### My git-steps how-to file
#git #howto

git init
git branch -M main
git status
git add .
git commit -m ""
git push


##### HOW TO CREATE A BRAND NEW REPO
0. after creating a new empty repo (e.g., "saint-eyeball") on the github website:
1. create new directory and put a file in it.
2. git init
3. git branch -M main
4. create .gitignore: put the names of possible binaries here so they do not get uploaded. a.out. do not put the directory name here.
5. git remote add origin git@github.com:thrillfreak23/saint-eyeball.git
  - ***Nota Bene***: *do not use https@!!! Use git@!!!*
6. git add .
7. git commit -m "comment goes here"
8. git push -u origin main
9. ***git push*** :: after the first time if the name "main" is used

##### The Basic Process after inital creation
1. from the Linux command line
2. git add .
3. git commit -m "Manual Update"
4. git push 