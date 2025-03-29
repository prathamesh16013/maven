
  mkdir mavenapp
  cd mavenapp/
  mkdir -p src/main/com/fortune/myapp  src/test/com/fortune/myapp
  sudo apt install tree 
  tree
  sudo nano pom.xml
  sudo nano src/main/com/fortune/myapp/App.java
  sudo nano src/test/com/fortune/myapp/AppTest.java
  ls
  tree

  then create one Github repository : Set webhook to trigger Jenkins 
  payload url : http://public-ip/github-webhook/
  

  next login jenkins : 
  Do setup for Maven and JDK tool which is installed already while configuring Jenkins 1st time.
  Dashboard - Manage Jenkins -  Tools - JDK installations - Add JDK - Enter Name - install automatically

  add maven - Enter Name - install automatically - saveit

  Create new freestyle Project
  Dashboard - New Items : 
  genral - Description 
  SCM - git - add repolink
  build trigger - github hook trigger for GITScm polling
  environment - nochanges
  Build Step 
  Add - build step - Invoke top-level Maven targets - maven version(mymaven) -goals(clean package)

  Save it.
  Now push the code files to github repo:

  git init
  ls -a      #to show git hidden directory
  git config --global user.name "prathamesh16013"
  git config --global user.email "email-id"
  git config --list
  git remote add origin <repo-link>
  git pull <repo link>
  git status
  git add .
  git commit -m "my maven build and test"
  git push origin master
  give username and tokan
  

  Check on browser, your project started building :Check the workspace you will get .jar file there.

  Project 2: maven-test
  give name: Step 1: General: SCM - git (add repo link) - 
  Step 3: Build Trigger(build after other project- maven build) 
  Step 4: Build Environment
   (No changes)
  Step 5: Build steps
  Add build step à Invoke top-level maven targets(maven version - mymaven  goals -test)

  Save it and build your 1st project maven-build and check.
  
  
