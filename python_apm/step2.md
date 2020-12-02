Let's now download the small application and have it up and running.

1. Download the application:
`
git clone https://github.com/melvynator/simple-django-app.git
cd simple-django-app/
`{{execute}}

2. Let's create a virtual environment and then activate it:
`
virtualenv -p python3 venv
source venv/bin/activate
`{{execute}}

3. Let's install some dependencies:
`
pip install -r requirements.txt
`{{execute}}

4. The first thing to do is to to install the APM agent:
`
pip install elastic-apm
`{{execute}}

5. Go into the file named `settings.py` and uncomment the APM related line.

6. Add the information about your deployment. Replace URL by the URL of your
deployment and TOKEN, by your security token.

7. Finally let's test if your application is sending data correctly to your
deployment.
`
python manage.py elasticapm check
python manage.py elasticapm test
`{{execute}}

You should see an error in the APM UI in Kibana confirming that you are all set
up!
