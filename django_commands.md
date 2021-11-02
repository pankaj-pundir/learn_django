# Django commands
- django-admin startproject pollster
- python manage.py runserver 8081 [run the server ]
- python manage.py migrate

# create a new app within the project
- python manage.py startapp polls
- python manage.py makemigrations polls [migrate the classes[models] created within the polls ]

## add the poll conofig in the pollstar settings file
polls.apps.PollsConfig

# link the classes in admin.py
admin.site.register(Question)
admin.site.register(Choice)


- set the admin page title and headers 
admin.site.site_header = "Pollster Admin"
admin.site.site_title = "Pollster Admin Area"
admin.site.index_title = "Welcome to Pollster Admin"


# useful tricks
- python manage.py shell [opens an interactive shell]
    - from polls.models import Question, Choice
    - from django.utils import timezone
    - Question.objects.all()   
    - q = Question(question_text = "fav frmewrk?",pub_date = timezone.now())
        - the object is in the variable and not yet within the database
    - q.save() [save to database]

    - Question.objects.filter(id=1)
    - Question.objects.get(pk=1)

    - Choices
        - q.choice_set.all()
        - q.choice_set.create(choice_text = 'django',votes=0)

- quit()
- python manage.py createsuperuser [requires usrname, email and pswd]

- make templates in a common folder 
    - you can directly include th urls of one app to the settings.
    - 'DIRS': [os.path.join(BASE_DIR,'templates')],