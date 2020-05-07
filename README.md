#DevOps Assignment Work

I have followed these steps:

Repository:

1.Created a repository locally #Web using #Git_Bash

2.Initialize #Web and then created files #index.html and #web.html

3.Added these files to the #Staging_area using command: git add .

4.Connected #Web repo to my #GitHub account using : git remote add "nickname" git_repo_url

5.Commited all files to Github repo using git command: git commit . -m comment

6.Created two branches #master and #dev1 using command: git branch branch_name and git push -u branch_name.

7.Created a #git_hook called #post-commit using #bash_script and pushed #web.html from #dev1 branch using git commit . -m comments

Jenkins:

In Jenkins created jobs for different task:

Job1: #production_trigger1 and #production:

1.This will create a production environment.

2. Used POLLSCM for making triggers to fetch data in every 1 min using * * * * *

3.Connected with SCM using Git repository url.

4. Commands for environment creation:

· if sudo docker ps | grep prodenv

· then

· sudo docker rm -f prodenv

·  sudo docker run -dit -p 1212:80 -v /dev:/usr/local/apache2/htdocs --name prodenv httpd

·        else

· sudo docker run -dit -p 1212:80 -v /ishweb:/usr/local/apache2/htdocs --name prodenv httpd

· fi

5. Command for storing data which is fetched from github: sudo cp -rvf * /ishweb

6.Branch used: master

Job2: #dev_trigger1 and #developer:

1.This will create a testing environment name as devos.

2.Used POLLSCM for making triggers to fetch data in every 1 min using * * * * *

3.Connected with SCM using Git repository url.

4. Command for environment creation:

· if sudo docker ps | grep devos

· then

· sudo docker rm -f devos

· sudo docker run -dit -p 1213:80 -v /dev:/usr/local/apache2/htdocs --name devos httpd

· else

· sudo docker run -dit -p 1213:80 -v /dev:/usr/local/apache2/htdocs --name devos httpd

· fi

5. Command for storing data which is fetched from github:

·        sudo cp -rvf * /dev

6.Branch linked: dev1

Job3: QAT team

1.Created job #QAT as trigger by build trigger using remote url and authentication token.

2. Setup the SCM using git url and provide credentials username and password.

3. Setup additional behaviours merge before build.

4. Used #Post-build_Action Git publisher.

All done!!!

Here is my Git link : https://github.com/ManishVerma16/web

#VimalDaga #IIEC_RISE #DevOps #Jenkins #Right_Education #project #Assignment

 
