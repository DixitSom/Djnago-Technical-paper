# Django
## Architecture
Django is based on MVT architecture that is Model-View-Template.
It has following parts.

1. __Model__:- The Model is the interface of data. It is used to process and maintain the data. It is the Logical level schema of your database. Models are used to define the structure of you database. In relational databases you can create tables and fields of tables using these Django models.
2. __View__:- Django Views render the templates into your browser. Views is the interface that you see in a browser. View function is a python function that takes a web request and returns a web response.
3. __Template__:- Templates contains general HTML with some special syntax used to manage the dynamic behaviour of the Web frontend.

## Security in Django
These are some main security features that Djnago provide us. 

1. Cross site scripting (XSS) protection
2. Cross site request forgery (CSRF) protection
3. SQL injection protection
4. Clickjacking protection
5. Host header validation

## About settings.py File in Djnago

### BASE_DIR
 Line:
 ```
 BASE_DIR = os.path.dirname(os.path.dirname(os.path.abspath(__file__)))
 ```

 BASE_DIR points to base directory or project if you created a project ```myproject``` then BASE_DIR will be ```~/myproject```.

 ### DEBUG
 Line:
 ```
 DEBUG = True
 ```

 Django provides a inbuild debugger which makes our life easier during development. So in order to enable it this DEBUG should be set to ```True```. In production we have to set it to ```False```.

 ### ALLOWED_HOSTS
 Line:
 ```
 ALLOWED_HOSTS = []
 ```
 ALLOWED_HOSTS is the list of all domains which can run your project. It can be empty during development because default is ```localhost``` or ```127.0.0.1 ```.
 In production it can not be empty.

 ### INSTALLED_APPS
 Line:
 ```
 ¸ = [
        ...,
        ...,
        ...,
        'yourApp', // don't forget to quote it and also commas after every app
]
 ```
 It containes list of all apps used by your Django project. You have to add here every newly created app.

 ### DATABASES
 Line:
 ```
 DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.sqlite3',
            'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
        }
    }
 ```
 This is used to define the database that we are using. Default is set to sqlite3. For using PostgreSQL you do this.
 ```
DATABASES = {
     'default': {
         'ENGINE': 'django.db.backends.postgresql',
         'NAME': YOUR_DB_NAME,
         'USER': USERNAME,
         'PASSWORD': PASSWORD_FOR_DB,
         'HOST': 'localhost'  // in Development.
     }
 }
 ```

### MEDIA_URL
Line
```
MEDIA_URL= '/media/'
```
MEDIA_URL is relative path to BASE_DIR. This variable is use to store the media files.

### STATIC_URL
Line:
```
STATIC_URL = '/static/'
```
STATIC_URL is relative path to BASE_DIR. This variable is use to store the static files. 

### MEDIA_ROOT
Line:
```
MEDIA_ROOT= os.path.join(BASE_DIR, 'media')
```
MEDIA_ROOT is absolute path. This variable is use to retrieve the media files. 

### STATIC_ROOT
Line:
```
STATIC_ROOT= os.path.join(BASE_DIR, 'static')
```
STATIC_ROOT is absolute path. This variable is use to retrieve the static files. 
