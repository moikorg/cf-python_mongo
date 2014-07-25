Sample Python Web application connecting to MongoDB
===================================================

The sample is using [Flask microframework](http://flask.pocoo.org/) and mongoengine. It is intented to test the Python
support on [Pivotal's Cloud Foundry](https://run.pivotal.io/).

The script tries to get the environment information to know how to connect to the MongoDB. It reads the
**VCAP_SERVICES** information and looks for the MongoDB information.

The script writes some dummy information to the database.

The web application listens to the following URLs
* ../env
* ../cred
* ../<username>/show --> where <username> is one of the dummy information username (e.g. donald, dagobert, ... see the code)

Deploy to Cloud Foundry
-----------------------
```script
cf push hello-python -b https://github.com/joshuamckenty/heroku-buildpack-python.git
```

The Procfile file contains the instructions to CF how to start the application. The used build pack works fine for this example,
other buildpacks for Python also exists, but hasn't been tested here.

The runtime.txt file contains the needed Python version and the requirements.txt files contains the Python library which
has to been loaded and installed by CF.

Have fun with Python and MongoDB on cloudfoundry!!

  Cheers, Mike