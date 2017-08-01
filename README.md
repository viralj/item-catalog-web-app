@@ -1,2 +1,73 @@
# Item Catalog Web App
This web app is a project for the Udacity [Full Stack Web Developer Nanodegree Course](https://www.udacity.com/course/full-stack-web-developer-nanodegree--nd004).

## About
This project is RESTful Web application built with Flask framework written Python language. This project used Google's OAuth for login authentication. 

## In This Repo
This project has one main Python module `app.py` which runs the Flask application. 
The Flask application uses HTML templates stored in the templates folder to render the front-end of the application. 
The static directory contains CSS/JS/Images folders and files.

## Used
1. Python
2. HTML
3. CSS
4. OAuth
5. Flask Framework

## This application requires
- [Vagrant](https://www.vagrantup.com/)
- [Udacity Vagrantfile](https://github.com/udacity/fullstack-nanodegree-vm)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

## How to Install and run
1. Install Vagrant & VirtualBox
2. Clone the Udacity Vagrantfile
3. Go to Vagrant directory and either clone this repo or download and place zip here
3. Launch the Vagrant VM (`vagrant up`)
4. Log into Vagrant VM (`vagrant ssh`)
5. Navigate to `cd/vagrant` as instructed in terminal
6. The app imports requests which is not on this vm. Run sudo pip install requests
7. Setup application database `python /item-catalog/database_setup.py`
8. *Insert fake data `python /item-catalog/database_init.py`
9. Run application using `python /item-catalog/app.py`
10. Access the application locally using http://localhost:8900

*Optional step(s)

## Using Google Login
To get the Google login working there are a few additional steps:

1. Go to [Google Dev Console](https://console.developers.google.com)
2. Sign up or Login if prompted
3. Go to Credentials
4. Select Create Credentials > OAuth Client ID
5. Select Web application
6. Enter name 'Item-Catalog'
7. Authorized JavaScript origins = 'http://localhost:8900'
8. Authorized redirect URIs = 'http://localhost:8900/login' && 'http://localhost:8900/gconnect'
9. Select Create
10. Copy the Client ID and paste it into the `data-clientid` in login.html
11. On the Dev Console Select Download JSON
12. Rename JSON file to client_secrets.json
13. Place JSON file in item-catalog directory that you cloned from here
14. Run application using `python /item-catalog/app.py`

## JSON Endpoints
The following are open to the public:

Catalog JSON: `/catalog.json`
    - Displays the whole catalog. Categories and all items.

Categories JSON: `/catalog/categories.json`
    - Displays all categories

Category Items JSON: `/catalog/<path:category_name>/items.json`
    - Displays items for a specific category

Category Item JSON: `/catalog/<path:category_name>/<path:item_name>/json`
    - Displays a specific category item.
