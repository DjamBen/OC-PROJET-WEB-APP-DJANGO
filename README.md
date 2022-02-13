# PROJECT 9 : Développez une application Web en utilisant Django


## Context

Creation of a web application allowing users to request reviews of books or articles by creating a ticket and to publish reviews of articles or books.

## Installation


### 1 - Installing the virtual environment tool
    
For run this script you need to install Python 3 For run chess tournament you need to install requirement.txt for import all necessary package. You can install virtual environment and run script in your venv.

step:

python -m venv venv # Install virtual environment
source venv/Scripts/activate # activate virtual environment
pip3 install -r requirement. txt


### 2 - Setting up the "env" virtual environment


    1 - Access to the project directory:
            
            sample cd /litreview_project

    2 - Creation of the virtual environment:
            
            $ python3 -m venv env


### 3 - Opening the virtual environment and adding modules

            (windows) env/script/activate or
            (linux) $source env/bin/activate
            
            (env) $ pip install -r requirements.txt
            

### 4 - Editing the litreview/litreview/settings_example.py file

    1 - Rename the settings_example.py file to settings.py

    2 - Modify the 'SECRET_KEY' variable to add a security key
        (53 random characters with uppercase,
        lower case, numbers and special characters)

    3 - Modify the 'DATABASES' variable in order to add
        the path to the database

            example:
            DATABASES = {
                'default': {
                    'ENGINE': 'django.db.backends.sqlite3',
                'NAME': BASE_DIR / 'db.sqlite3',
                }
            }

## Using the program


### 1 - Launch

    1 - activation of the virtual environment in the base directory:

        source env/bin/activate

    2 - access to the litreview directory:

        cd litreview/

    3 - Launching the Django server

        ./manage.py runserver

    4 - Opening a web page
    
        Address: 127.0.0.1:8000

### 2 - Use

    In order to test the site, 5 fictitious users are registered with some tickets and reviews
    in the "db.sqlite3" database made available in the repository:

        - leon28
        - jean35

        the password for users: P@ssword1


    To have an initial database:

        1 - Stop the Django server by performing the combination:
                
                 control+c

        2 - Delete the "db.sqlite3" file

        3 - migrate to the new database

                ./manage.py makemigrations => This creates a file in litreview/review/migrations
              
### Creating a user

    On the 'Connection' page accessible from the address "127.0.0.1:8000", a "register" button allows
    to access the 'Registration' page.

    On this page, we enter a name which will be the identifier and a password twice to confirm it.
    This password must have at least 8 characters, a capital letter, a number and a special character.

###  Use of the site

- The Feeds page:

    -   Once the user is logged in, the "feed" page is displayed.

        The user can create a ticket to request a review of a book or
        directly make a review by creating the ticket followed by the review.

        A feed of tickets and reviews is displayed by creation date in descending order.
        these are the user's tickets and reviews or those of followed users.

        If a ticket does not have a corresponding review, it is possible to make one.

        When a ticket has had a review, it no longer appears in the feed. It appears directly in the review.
        It is then no longer possible to add a review to this ticket.


    - The Post page:

        This page displays all of the user's tickets and reviews.
        It is then possible to modify these posts or delete them.

        If a ticket containing a review is deleted, then the review is also deleted.

        If a review is deleted, it will then be possible to perform a review again.


    - The Subscription page:

        This page allows the management of followed users.

        You can add a user by entering his name or unsubscribe from this user.

        By following a user, we see the posts created by this user and thus respond to tickets.
