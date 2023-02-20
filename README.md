CREATED CI CD PIPELINE OF A WEB APP USING DOCKER JENKINS AWS

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
1 sudo apt-get update  -y
2 sudo yum install git -y
3 git clone https://github.com/Abzalbasha/django-todo.git
4 cd django-todo/
Step1: sudo apt-get update.
Step2: sudo apt-get install python3-pip
5 pip3 install django
6 python3 manage.py migrate
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


    :wq

    code = 
    FROM python:3
RUN pip3 install django==3.2
COPY . .

RUN python3 manage.py migrate

CMD ["python3","manage.py","runserver","0.0.0.0:8000"]



docker build . -t todo-App
error
 Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Post "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/build?buildargs=%7B%7D&cachefrom=%5B%5D&cgroupparent=&cpuperiod=0&cpuquota=0&cpusetcpus=&cpusetmems=&cpushares=0&dockerfile=Dockerfile&labels=%7B%7D&memory=0&memswap=0&networkmode=default&rm=1&shmsize=0&t=todo-app&target=&ulimits=null&version=1": dial unix /var/run/docker.sock: connect: permission denied

solution
sudo docker build . -t todo-app

sudo docker ps
 to check contianer running or not 

sudo docker run  port mapping and  container id 
sudo docker run -p 8000:8000 c548344894
sudo docker run -d -p 8000:8000 c548344894 
to run in background use -d


Jnekins
 installation of jenkins 


























