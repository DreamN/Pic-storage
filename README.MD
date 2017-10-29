# Pic-Storage
pic-storage is the project for uploads and store images to the server.

This project using flask (A python web microframework).

This project is under the MIT License.

## To run the application

- Edit the Database Configuration file (settings.py)

```python
    DATABASE_NAME = 'YOUR_DATABASE_NAME'
    DATABASE_USER = 'YOUR_USER'
    DATABASE_HOST = 'YOUR_DATABASE_HOST'
    DATABASE_PASSWORD = 'YOUR_PASSWORD'
```
- Create the database table (for the first time) and install packages
     
     run the code below - make sure permission is set ( chmod +x setup.sh )
```
  $ ./setup.sh
```


- Run the app

```
  $ python app.py
```

## To deploy application

- Configure and enable new virtual host - /etc/<your-server-directory>/<configuration-file>>

- Be sure to change the ServerName to your domain or cloud server's IP address.

- Create .wsgi file 

```python
    #!/usr/bin/python
    import sys
    import logging
    logging.basicConfig(stream=sys.stderr)
    sys.path.insert(0,"/var/www/FlaskApp/")

from FlaskApp import app as application
application.secret_key = 'Add your secret key'
```

