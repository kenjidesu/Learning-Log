# Learning Log
![Topics](https://github.com/kenjidesu/Learning-Log/blob/main/register.PNG)


A web app called *Learning Log* that allows users to log the topics they've interested in and to make journal entries as they learn about each topic.
The *Learning Log* homepage will describe the site and invite users to either register or log in. Once logged in, a user can create new topics, add
new entries, and read and edit existing entries.

## How to run:
  - Step 1: Clone the repository\
    `git clone https://github.com/kenjidesu/Learning-Log`
  
  - Step 2: Create Virtual environment\
    `python -m venv ll_env`
  
  - Step 3: Activate the Virtual environment\
    Windows: `ll_env\Scripts\activate`\
    Mac: `source ll_env/bin/activate`
    
  - Step 4: Install django-bootsrap4\
    `pip install django-bootstrap4`
    
  - Step 5: Create a project in django\
    `django-admin startproject learning_log .`
    
    *Note: Don't forget this dot, or you might run into some configuration issues when you deploy the app.
          If you forget the dot, delete the files and folders that were created (except ll_env), and run the command again.*
      
  - Step 6: Modify\
    ***settings.py:***
    ```
    --snip--
    INSTALLED_APPS = [
      # My apps
      'learning_logs',
      'users',

      # Third party apps
      'bootstrap4',

      # Default django apps
      'django.contrib.admin',
      'django.contrib.auth',
      'django.contrib.contenttypes',
      'django.contrib.sessions',
      'django.contrib.messages',
      'django.contrib.staticfiles',
    ]
    ```
    At the end of the `settings.py` add:\
    `LOGIN_URL = 'users:login'`
    
    ***urls.py:***
    ```
    from django.contrib import admin
    from django.urls import path, include

    urlpatterns = [
        path('admin/', admin.site.urls),
        path('users/', include('users.urls')),
        path('', include('learning_logs.urls')),
    ]
    ```
  - Step 7: View the project on your system\
    `python manage.py runserver`\
    *Open a web browser and enter the URL ***http://localhost:8000****
    
