# django-todo
A simple todo app built with django

![todo App](https://raw.githubusercontent.com/shreys7/django-todo/develop/staticfiles/todoApp.png)
### Setup
To get this repository, run the following command inside your git enabled terminal
```bash
$ git clone https://github.com/shreys7/django-todo.git
```
You will need django to be installed in you computer to run this app. Head over to https://www.djangoproject.com/download/ for the download guide

Once you have downloaded django, go to the cloned repo directory and run the following command

```bash
$ python manage.py makemigrations
```

This will create all the migrations file (database migrations) required to run this App.

Now, to apply this migrations run the following command
```bash
$ python manage.py migrate
```

One last step and then our todo App will be live. We need to create an admin user to run this App. On the terminal, type the following command and provide username, password and email for the admin user
```bash
$ python manage.py createsuperuser
```

That was pretty simple, right? Now let's make the App live. We just need to start the server now and then we can start using our simple todo App. Start the server by following command

```bash
$ python manage.py runserver
```

Once the server is hosted, head over to http://127.0.0.1:8000/todos for the App.

Cheers and Happy Coding :)

pip freeze > requirments.tx , 
this  file shows what reuirments needed



CODE process 
1 version control system local 

2 in server errors arrive  and steps needed for docker wee need

* apt-get update
1 sudo yum update  -y
2 sudo yum install git -y
3 git clone https://github.com/Abzalbasha/
4 cd django-todo/
Step1: sudo apt-get update.
Step2: sudo apt-get install python3-pip
5 pip3 install django
6 python manage.py migrate
Chnage time zone
7 python3 manage.py runserver
127.0.0.1:8000/ means run on local host , if u want to expose to world  uit shoud be 0.0.0.0
python3 manage.py runserver 0.0.0.0:8000
8 in aws enable tcp port 8000 everywhere in security groups
9 and allow that in seeting.py file which shows in browser upadte that ip in file in djangp setting.py file add ip or '*' in allowed host
10 nohup python3 manage.py runserver 0.0.0.0:8000 & 
it gives ignore input gives output in a file using & and nohup 
11 lsof -i: 8000  
it gives what process task runnning on port 8000
12 kill -9 portnumber
we can stop process by this

NOW CREATING DOCKER AND ADDING DJANGO FILE IN THAT
    sudo apt install docker.io
    vi Docker file  add all docker commands which we did manually

    * python

    FROM python:3 # creates a environment ubuntu where python3 running

    RUN pip3 install django==3.3 # running command install django with version 3.2

    * code
    COPY . .  # copy code from source to destination first dot source second dot destinantion


    * Run 
    RUN python3 manage.py migrate # which migrates manage file using run 

    
    CMD ["python3","manage.py","runserver","0.0.0.0:8000"]




