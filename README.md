# django-crontab to run flushexpiredtokens
Implementation of django-crontab to run flushexpiredtokens
<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="">
    <img src="https://live.staticflickr.com/7472/16199272841_dffe0b2873_c.jpg"  width="400" alt="Header" >
  </a>
   <div align="center">
   <a href="https://www.facebook.com/aldo.matusmartinez" ><img src="https://github.com/edent/SuperTinyIcons/blob/master/images/svg/facebook.svg" title="Facebook" width="60"  margin="30px"/></a><a href="https://github.com/aldomatus/" ><img src="https://github.com/edent/SuperTinyIcons/blob/master/images/svg/github.svg" title="Github" width="60"/></a><a href="https://www.instagram.com/aldomatus1/" ><img src="https://github.com/edent/SuperTinyIcons/blob/master/images/svg/instagram.svg" title="Instagram" width="60"  /></a><a href="https://www.linkedin.com/in/aldomatus/" ><img src="https://github.com/edent/SuperTinyIcons/blob/master/images/svg/linkedin.svg" title="Linkedin" width="60"  /></a>

  </div>
  <h1 align="center">THIS PROJECT WAS MADE TO LEARN TO USE THE CRONTAB TO RUN FLUSHEXPIREDTOKENS </h1>
  <h3 align="center">Learn REST API with Django Rest Framework and Mysql</h3>
</p>



<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project
In this project we will see the Implementation of django-crontab to execute flushexpiredtokens and eliminate the tokens from the Outstanding tokens and Blacklisted tokens generated with Simple JWT list.

### Built With

Frameworks and libraries.
Framewrok:
* [Django](https://www.djangoproject.com/)
* [Django Rest Framework](https://www.django-rest-framework.org/)

Libraries:
* [django-crontab](https://pypi.org/project/django-crontab/)
* [django-rest-framework-simplejwt](https://django-rest-framework-simplejwt.readthedocs.io/en/latest/)

<!-- GETTING STARTED -->
## Getting Started
### To check your rest api
#### Insomnia

With their streamlined API client, you can quickly and easily send REST, SOAP, GraphQL, and GRPC requests directly within Insomnia.
Link to visit insomnia website: - [Link](https://insomnia.rest/download)
<div align="center">
 <img src=https://seeklogo.com/images/I/insomnia-logo-A35E09EB19-seeklogo.com.png width="150" alt="Header" >
  </div>


#### Postman
Postman is a collaboration platform for API development. Postman's features simplify each step of building an API and streamline collaboration so you can create better APIs—faster.
Link to visit postman website: - [Link](https://www.postman.com/downloads/)
<div align="center">
 <img src=https://seeklogo.com/images/P/postman-logo-F43375A2EB-seeklogo.com.png width="150" alt="Header" >
</div>

### Prerequisites
In this example we use simple jwt with django rest framework, you must have a jwt implementation to generate the tokens that will be sent to the Blacklisted token and Outstanding tokens

### Installation 🖥

1. To obtain my repository you must create a folder in a desired directory and within this folder open a terminal or use cmd in the case of windows.
2. Clone the repo
   ```
   git clone git@github.com:aldomatus/django-crontab-to-run-flushexpiredtokens.git
   
   ```
3. Make the pull request from a branch called main
   ```
   git fetch
   git checkout origin master
   git pull origin master
   ```

   ```
   http://localhost:8000/admin/
   ```


## Description of the files 💼 🐳
### requirements.txt
In our requirements file we write the flask libraries, the connection libraries for msql and with which we are going to manage the SQL data
```python
asgiref==3.4.1
Django==3.2.7
django-common-helpers==0.9.2
django-cors-headers==3.8.0
django-cron==0.5.1
django-crontab==0.7.1
django-environ==0.7.0
django-rest-auth==0.9.5
djangorestframework==3.12.4
djangorestframework-simplejwt==4.8.0
mysqlclient==2.0.3
Pillow==8.3.2
PyJWT==2.1.0
pytz==2021.1
six==1.16.0
sqlparse==0.4.2
```

### .env file 🌍
This file contains our environment variables that will be read by the dockerfile. 

```
FLASK_DEBUG=True
FLASK_APP=src/main.py
FLASK_RUN_HOST=0.0.0.0
ALLOWED_HOSTS=127.0.0.1,localhost
```

## django-crontab implementaction
install via pip:
```
pip install django-crontab
```
add it to installed apps in django settings.py:
```
INSTALLED_APPS = (
    'django_crontab',
    ...
)
```
now create a new method that should be executed by cron every 5 minutes, f.e. in myapp/cron.py:

```
def my_scheduled_job():
  pass
 ```
```
# Example
import os
import sys

def flushexpiredtokens():
    os.system('GREPDB="cd /home/aldo/Documents/independent_projects/wpo-back/ && source .venv/bin/activate && python3 manage.py flushexpiredtokens > /dev/null 2>&1"; /bin/bash -c "$GREPDB"')
```
now add this to your settings.py:
```
CRONJOBS = [
    ('*/5 * * * *', 'myapp.cron.my_scheduled_job')
]
```
```
# Example
CRONJOBS = [
    ('*/1 * * * *', 'Apps.users.cron.flushexpiredtokens')
    ]
```

### 


<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.



<!-- CONTACT -->
## Contact

Aldo Matus - [Linkedin](https://www.linkedin.com/in/aldomatus/) [Facebook](https://www.facebook.com/aldo.matusmartinez/)

Project Link: [Repository](https://github.com/aldomatus/flask_rest_api/)






