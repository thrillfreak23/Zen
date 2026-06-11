# Git steps - git howto



 My git-steps how-to file
#git
git init
git branch -M main
git status
git add .
git commit -m ""
git push


after creating a new empty repo "saint-eyeball" on the github website:

1. create new directory and put a file in it.
2. git init
3. git branch -M main
4. create .gitignore: put the names of possible binaries here so they do not get uploaded. a.out. do not put the directory name here.
5. git remote add origin git@github.com:thrillfreak23/saint-eyeball.git
6. git add .
7. git commit -m "whatever"
8. git push -u origin main
9. can be just ***git push*** after the first time if the name "main" is used

## The Basic Process after inital creation
1. from the Linux command line
2. git add .
3. git commit -m "Manual Update"
4. git push 