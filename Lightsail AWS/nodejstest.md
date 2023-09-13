### NODE-JS TEST API-DEV
----------------------------------

* First we need to install some dependices to that server like GitlaB, Node-js, Forever, PM2.
*  Some times we can't use the forever because it shuold only the file not the whole branch. So we use the pm2 to run background same like forever here we can run our direct command.
* Refer Here for pm2 commands 
   
   ![refer here]https://pm2.keymetrics.io/docs/usage/quick-start/

* we already know how install a gitlab-ce in the server refer the documentation for process.
  ``` 
  sudo apt install npm
  sudo npm instal forever
  ```
  ```
  sudo npm install -g pm2
  pm2 start --name my-app "sudo npm run dev"
  pm2 list
  pm2 show my-app
  ```
* If you don't have pm2 installed, you can install it globally using npm.
* You can use pm2 to run your sudo npm run dev command in the background. Open your terminal and navigate to the directory where your Node.js application is located. Then run.
* Here, "my-app" is a user-defined name for your process. You can choose any name you like.
* You can monitor the status of your application and view logs using pm2 commands. For example
* To view detailed information about a specific process (replace my-app with your process name or ID):pm2 show my-app
  
  ![pre](Images/f14.png)
  ![pre](Images/f10.png)
  ![pre](Images/F11.png)



* To DELETE or STOP the pm2 process we have one commands if it doesn't stop with that command we have to do direct kill process.

  ```
  pm2 delete my-app or id number

  ``` 
  ```
  sudo lsof -i :3001
  kill -9 pid number 
  ```
  ![pre](Images/f13.png)

* Now we need to take the code from git lab server for the first time we need to take the gitclone link from gitlab server like below.
  
  ![pre](Images/f7.png)

* when we want to just pull the new code changes we can do git pull

  ![pre](Images/f1.png)

* After that go the particular path or folder where the code is present. So we have ICS & MoneyBridge, In ICS i have index.js  file so i need to run that file here i should we the forever command.
* We can stop forever stop and pid number from any folder, But we can't start the .js file from any where unless your in particular folder

  ![pre](Images/f3.png)
  ![pre](Images/f6.png)
  ![pre](Images/f5.png)

* Here we can see the forever logs files. For that we have to be a root user in that if do below command.

  ```
  cd /root/.forever/
  ```
  ![pre](Images/f4.png) 

* so here some forever command we can see the list of background running file through forever.
  
  ![pre](Images/f2.png)

  ```
  forever start <filename>
  forever stop <pid no>
  forever list
  forever --help
  ```
* As you can see now we had run the both code of ICS & MoneyBridge parallel in the single server with different ports with forever.
 
  ![pre](Images/f8.png)
  ![pre](Images/f9.png)