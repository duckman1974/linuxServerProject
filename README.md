Linux Project - Udacity

  Server details -

  IP = 18.219.102.160

  URL: http://ec2-18-219-102-160.us-east-2.compute.amazonaws.com/

  SSH PORT: 2200

Summary of software installed:

- upgraded all available Ubuntu packages
  - sudo apt-get update
  - sudo apt-get upgrade

- installed apache2 webserver
  - sudo apt-get install apache2

- installed PostgreSQL for Database
  - sudo apt-get install postgresql postgresql-contrib
  "Documentation referenced: https://www.digitalocean.com/community/tutorials/how-to-secure-postgresql-on-an-ubuntu-vps"

- installed GIT
  sudo apt-get Git

- installed Flask and virtual environment and app dependencies
  - sudo pip install Flask
  - sudo pip install sqlalchemy
  - sudo pip install Flask-SQLAlchemy
  - sudo pip install psycopg2
  - sudo apt-get install python-psycopg2
  - sudo pip install oauth2client
  - sudo pip install httplib2
  - sudo pip install requests


Configuration Changes:

  Updated and upgrade Ubuntu to the most recent packages

  Created a new user called: grader

  Modified "grader" to have sudo rights
  "Documentation referenced: https://www.digitalocean.com/community/tutorials/how-to-add-and-delete-users-on-an-ubuntu-14-04-vps"

  Setup public/private key for user grader and disabled password login

  Disabled root login to the Server

  Enabled port 2200 - ssh, 80 - web, 123 - ntp and enabled Ubuntu firewall (ufw)

  Disabled port 22 - ssh

  Installed apache webserver

  Modified the local time to UTC
  "Documentation reference: https://askubuntu.com/questions/138423/how-do-i-change-my-timezone-to-utc-gmt/138442"

  Installed Postgresql and created Admin user postgres

  Created a new user called catalog and altered role and privileges
  "Docmentation reference: https://www.postgresql.org/docs/8.0/static/sql-createuser.html"

  Disabled public access to catalog DB and only granted access to catalog user

  Created a Virtual Environment for the application to run in call "venv"

  Enabled the catalog.conf

  Created a catalog.wsgi config
  "Docmentation reference: https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps"

  In the Database_setup.py and __init__.py (formally 'view.py') changed the original db connection from sqlite to PostgreSQL

  Changed the Google OAuth parameters in the google developer's credentials to allow for the javascript origin and url redirect to
  work with AWS
    - javascript origins: http://ec2-18-219-102-160.us-east-2.compute.amazonaws.com
    - authorized redirects: http://ec2-18-219-102-160.us-east-2.compute.amazonaws.com/login and
                            http://ec2-18-219-102-160.us-east-2.compute.amazonaws.com/gconnect
