## 🔥 How to host your python flask website free in Heroku 🔥

**What is Flask?**

Flask is a web application framework written in Python. Flask is based on the Werkzeug WSGI toolkit and Jinja2 template engine. Both are Pocco projects. This post revolves around how to deploy a flask app on Heroku. To demonstrate this, we are first going to create a sample application for a better understanding of the process. 

**Prerequisites: **

- Python
- pip
- Git
- VS code(editor)

**STEP 1 :** Let’s create a simple flask application first and then it can be deployed to heroku. Create a folder named ["eagle_programming"](https://www.instagram.com/eagle_programming/?hl=en) on your computer. Open that folder in VS code editor and create a “Procfile” and write the following code.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1654085166689/QTThYon1v.png align="left")

**STEP 2 :** Create “requirements.txt” and write the following requirements.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1654085233119/CYs0PmJM3.png align="left")

**STEP  3:**Create [app.py](https://github.com/naveenkumar-j/heroku-tutorial) and write the following code.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1654085272789/72TKg0ZbU.png align="left")

**STEP 4:** Initialize an empty repo, add the files in the repo and commit all the changes.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1654085330198/1TyZ-jRkZ.png align="left")

**STEP 5 : **Create account in [Heroku](https://dashboard.heroku.com/login) and Login to heroku CLI using "heroku login" command and Now, Create a unique name for your Web app.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1654085384519/J1XeVvqay.png align="left")

**STEP 6:** Push your code from local to the heroku remote. 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1654085442046/wqa2gTGNE.png align="left")
Finally, our web app will be deployed on https://eagleprogramming.herokuapp.com/
 
